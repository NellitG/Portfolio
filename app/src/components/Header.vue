<template>
  <div>
    <!-- Header section -->
    <header
      :class="{
        'h-14 lg:h-36 fixed w-full top-0 inset-0 z-20 bg-white': isHomePage,
        'h-14 lg:h-24 fixed w-full top-0 inset-0 z-20 bg-white': !isHomePage,
      }"
    >
      <!-- Navigation specific to homepage -->
      <!-- <section v-if="isHomePage" class="bg-pink-400 py-4">
        <div class="flex justify-start items-center list-none px-5 space-x-10">
          <ul class="flex gap-5">
            <li>
              <router-link
                to="/techhub"
                class="text-white hover:text-gray-900"
                @click.native="closeMenu"
                >Innovation-hub</router-link
              >
            </li>
            <li>
              <router-link
                to="/contact"
                class="text-white hover:text-gray-900"
                @click.native="closeMenu"
                >Enquiries</router-link
              >
            </li>
          </ul>
        </div>
      </section> -->

      <!-- Header content -->
      <div
        class="flex items-center justify-between mx-auto max-w-7xl h-full px-4 lg:px-0"
      >
        <!-- Logo and menu toggle button -->
        <div class="flex items-center gap-6">
          <button
            class="text-2xl p-1 text-black hover:text-blue-500 lg:hidden"
            @click="toggleMenu2"
          >
            {{ close2 ? "☰" : "✘" }}
          </button>
          <router-link
            to="/"
            class="flex items-center"
            @click.native="closeMenu"
          >
            <img
              src="../assets/logos.jpg"
              alt="Logo"
              class="h-8 lg:h-20 mb-0 mt-6 ml-0"
            />
          </router-link>
        </div>

        <!-- Navigation menu -->
        <nav
        :class="{ hidden: close2, flex: !close2 }"
        class="bg-black lg:bg-white lg:static lg:flex lg:items-center flex-1 justify-center absolute top-14 lg:top-0 left-0 w-full lg:w-auto"
        >

          <!-- Navigation items -->
          <ul
            class="flex flex-col lg:flex-row gap-6 lg:gap-8 text-white lg:text-black mt-4 lg:mt-0 lg:items-center px-4 lg:px-0"
          >
            <li>
              <router-link
                to="/"
                class="hover:text-green-500"
                active-class="hover:text-green-500"
                @click.native="closeMenu"
                >Home</router-link
              >
            </li>
            <li class="relative group">
              <router-link
                to="/programs"
                class="hover:text-green-500 flex items-center"
                active-class="hover:text-green-500"
                @click.native="closeMenu"
              >
                <span>Programs</span>
                <span class="ml-1"></span>
              </router-link>
              <!-- <div
                class="absolute hidden group-hover:block lg:bg-gray-100 bg-blue-500 text-gray-900 p-4 rounded mt-2 lg:mt-0 lg:w-96 left-0 w-96"
              >
                <div class="grid grid-cols-2 lg:gap-4">
                  <div>
                    <router-link to="/schoolofbusiness">
                      <h3 class="font-semibold">School of Business</h3>
                    </router-link>

                    
                  </div>
                  <div>
                    <router-link to="/schoolofict">
                      <h3 class="font-semibold">School of ICT</h3>
                    </router-link>

                   
                  </div>
                  <div>
                    <router-link to="/schoolofhospitality">
                      <h3 class="font-semibold">School of Hospitality</h3>
                    </router-link>

                    
                  </div>
                  <div>
                    <router-link to="/schoolofengineering">
                      <h3 class="font-semibold">School of Engineering</h3>
                    </router-link>
                  </div>
                  <div>
                    <router-link to="/schoolofcosmetology">
                      <h3 class="font-semibold">
                        School of Beauty/Cosmetology
                      </h3>
                    </router-link>
                  </div>
                </div>
              </div> -->
            </li>
            <li>
              <router-link
                to="/aboutus"
                class="hover:text-green-500"
                active-class="hover:text-fuchsia-500"
                @click.native="closeMenu"
                >About Us</router-link
              >
            </li>
            <!-- <li>
              <router-link
                to="/news"
                class="hover:text-green-500"
                @click.native="closeMenu"
                >News & updates</router-link
              >
            </li> -->
            <li>
              <router-link
                to="/contact"
                class="hover:text-green-500"
                active-class="hover:text-green-500"
                @click.native="closeMenu"
                >Contact Us</router-link
              >
            </li>
            <li>
              <router-link
                to="/getinvolved"
                class="hover:text-green-500 relative"
                active-class="hover:text-green-500"
                @click.native="closeMenu"
              >
                Get Involved
               
              </router-link>
            </li>
          </ul>
          <!-- <div class="lg:flex lg:justify-end lg:items-end pr-8 space-x-3 hidden pt-4">
      <a href="#" class="px-6 py-2 bg-white hover:bg-teal-500 hover:text-white rounded-full pr-8 border-2 border-teal-500 text-teal-500 text-center">Login</a>
          </div> -->
        </nav>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  data() {
    return {
      close2: true,
    };
  },
  computed: {
    isHomePage() {
      return this.$route.path === "/";
    },
  },
  watch: {
    $route(to, from) {
      if (to.path === "/") {
        this.close2 = true;
      }
    },
  },
  methods: {
    toggleMenu2() {
      this.close2 = !this.close2;
    },
    closeMenu() {
      this.close2 = true;
    },
  },
  mounted() {
    if (this.isHomePage) {
      this.close2 = true;
    }
  },
};
</script>

<style scoped>
button {
  font-size: 2rem;
}
</style>
