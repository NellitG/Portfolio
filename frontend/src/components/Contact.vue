<template>
  <div class="py-0 mt-32">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="text-center">
        <h1
          class="mt-2 text-4xl font-semibold text-transparent bg-clip-text bg-gradient-to-r from-blue-900 to-yellow-500"
          style="font-family: 'Finger Paint', cursive"
        >
          Give us your Feedback or Comment
        </h1>
        <p class="text-gray-600 mt-4">
          Let us know how we can improve. Fill out the form below!
        </p>
      </div>
      <div class="mt-10 flex flex-col lg:flex-row gap-10">
        <!-- Left Section -->
        <div class="lg:w-1/2">
          <div class="bg-white p-6 rounded-lg shadow-md">
            <img
              src="https://res.cloudinary.com/dqe69vaz7/image/upload/v1738737483/medium-shot-kid-holding-smartphone_23-2148860434_ngz5ab.jpg"
              alt="Contact Us"
              class="w-full rounded-md mb-6"
            />
            <p class="text-gray-600 mb-4">
              Reach us today through our phone number or leave your feedback, and
              we will respond promptly.
            </p>
            <div>
              <p class="flex items-center text-gray-700 mb-2">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 mr-2 text-yellow-500"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                >
                  <path d="M2.003 5.884L10 1l7.997 4.884v8.232L10 19l-7.997-4.884V5.884z" />
                </svg>
                Phone: +254113984146
              </p>
              <p class="flex items-center text-gray-700">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5 mr-2 text-yellow-500"
                  viewBox="0 0 20 20"
                  fill="currentColor"
                >
                  <path
                    d="M4.228 2.634a8.007 8.007 0 0111.544 0l.866.866a8.007 8.007 0 010 11.544l-.866.866a8.007 8.007 0 01-11.544 0l-.866-.866a8.007 8.007 0 010-11.544l.866-.866z"
                  />
                </svg>
                Address: 937 Ngong Road, Nairobi
              </p>
            </div>       
          </div>
        </div>
        <!-- Right Section -->
        <div class="lg:w-1/2 hover:border-yellow-400 border-2 border-black-400 p-4">
          <div class="bg-white p-6 rounded-lg shadow-md">
            <form @submit.prevent="submitForm" class="space-y-4">
              <!-- Name -->
              <div>
                <label
                  for="name"
                  class="block text-sm font-medium text-yellow-500"
                  style="font-family: 'Finger Paint', cursive"
                >
                  Name
                </label>
                <input
                  type="text"
                  id="name"
                  v-model="formData.name"
                  required
                  class="mt-1 block w-full px-3 py-2 border rounded-md shadow-sm focus:ring-yellow-500 focus:border-yellow-500 sm:text-sm"
                  placeholder="Your Name"
                />
              </div>

              <!-- Email -->
              <div>
                <label
                  for="email"
                  class="block text-sm font-medium text-yellow-500"
                  style="font-family: 'Finger Paint', cursive"
                >
                  Email
                </label>
                <input
                  type="email"
                  id="email"
                  v-model="formData.email"
                  required
                  class="mt-1 block w-full px-3 py-2 border rounded-md shadow-sm focus:ring-yellow-500 focus:border-yellow-500 sm:text-sm"
                  placeholder="Your Email"
                />
              </div>

              <!-- Phone -->
              <div>
                <label
                  for="phone"
                  class="block text-sm font-medium text-yellow-500"
                  style="font-family: 'Finger Paint', cursive"
                >
                  Phone
                </label>
                <input
                  type="tel"
                  id="phone"
                  v-model="formData.phone"
                  pattern="\d{10,15}"
                  required
                  class="mt-1 block w-full px-3 py-2 border rounded-md shadow-sm focus:ring-yellow-500 focus:border-yellow-500 sm:text-sm"
                  placeholder="Your Phone"
                />
              </div>

              <!-- Message -->
              <div>
                <label
                  for="message"
                  class="block text-sm font-medium text-yellow-500"
                  style="font-family: 'Finger Paint', cursive"
                >
                  Message
                </label>
                <textarea
                  id="message"
                  v-model="formData.message"
                  rows="4"
                  maxlength="500"
                  required
                  class="mt-1 block w-full px-3 py-2 border rounded-md shadow-sm focus:ring-yellow-500 focus:border-yellow-500 sm:text-sm"
                  placeholder="Your Feedback/Comments"
                ></textarea>
              </div>

              <!-- Submit Button -->
              <div>
                <button
                  type="submit"
                  :disabled="isLoading"
                  class="w-full bg-yellow-500 text-white font-medium py-2 px-4 rounded-md"
                >
                  <span v-if="isLoading">Submitting...</span>
                  <span v-else>Submit</span>
                </button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      formData: {
        name: "",
        email: "",
        phone: "",
        message: "",
      },
      isLoading: false, // For submit button loading state
    };
  },
  methods: {
    async submitForm() {
      this.isLoading = true;
      try {
        const payload = {
          access_key: "3c025a31-6512-4329-8e9f-ce95c3c8ff28", // Web3Forms Public Key
          name: this.formData.name,
          email: this.formData.email,
          phone: this.formData.phone,
          message: this.formData.message,
        };

        const response = await axios.post("https://api.web3forms.com/submit", payload);

        if (response.data.success) {
          alert("Thank you for your feedback!");
          this.resetForm();
        } else {
          alert("Submission failed. Please try again later.");
        }
      } catch (error) {
        alert("An error occurred. Please check your connection and try again.");
      } finally {
        this.isLoading = false;
      }
    },
    resetForm() {
      this.formData = { name: "", email: "", phone: "", message: "" };
    },
  },
};
</script>
