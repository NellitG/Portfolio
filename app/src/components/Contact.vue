<template>
    <div class=" flex flex-shrink-0 flex-grow-0 items-center justify-center overflow-hidden">
            <a href="#" class="flex items-center gap-2 text-amber-500 hover:text-amber-500">
              <span class="flex-shrink-0 text-5xl font-semibold tracking-tight opacity-100">Contact Us</span>
            </a>
          </div>
    <div class="flex min-h-screen md:w-screen w-full items-center justify-center text-gray-600">
    <div class="relative">
      
  <div class="hidden sm:block h-56 w-56 text-amber-300 absolute a-z-10 -left-20 -top-20">
     <svg id='patternId' width='100%' height='100%' xmlns='http://www.w3.org/2000/svg'><defs><pattern id='a' patternUnits='userSpaceOnUse' width='40' height='40' patternTransform='scale(0.6) rotate(0)'><rect x='0' y='0' width='100%' height='100%' fill='none'/><path d='M11 6a5 5 0 01-5 5 5 5 0 01-5-5 5 5 0 015-5 5 5 0 015 5'  stroke-width='1' stroke='none' fill='currentColor'/></pattern></defs><rect width='800%' height='800%' transform='translate(0,0)' fill='url(#a)'/></svg>
    </div>
  <div class="hidden sm:block h-28 w-28 text-amber-300 absolute a-z-10 -right-20 -bottom-20">
     <svg id='patternId' width='100%' height='100%' xmlns='http://www.w3.org/2000/svg'><defs><pattern id='b' patternUnits='userSpaceOnUse' width='40' height='40' patternTransform='scale(0.5) rotate(0)'><rect x='0' y='0' width='100%' height='100%' fill='none'/><path d='M11 6a5 5 0 01-5 5 5 5 0 01-5-5 5 5 0 015-5 5 5 0 015 5'  stroke-width='1' stroke='none' fill='currentColor'/></pattern></defs><rect width='800%' height='800%' transform='translate(0,0)' fill='url(#b)'/></svg>
    </div>
      <!-- Register -->
      <div class="relative flex flex-col sm:w-[30rem] rounded-lg border-gray-400 bg-white shadow-lg px-4">
        <div class="flex-auto p-6">
          <!-- Logo -->
          
          <!-- /Logo -->
          <h4 class="mb-2 font-medium text-gray-950 xl:text-xl">Welcome to NellitG!</h4>
          <p class="mb-6 text-gray-500">Please sign-in to access your account</p>
  
          <form id="" class="mb-4" action="#" method="POST">
            <div class="mb-4">
              <label for="email" class="mb-2 inline-block text-xs font-medium uppercase text-gray-700">Email or Username</label>
              <input type="text" class="block w-full cursor-text appearance-none rounded-md border border-gray-400 bg--100 py-2 px-3 text-sm outline-none focus:border-amber-500 focus:bg-white focus:text-gray-950 focus:shadow" id="email" name="email-username" placeholder="Enter your email or username" />
            </div>
            <div class="mb-4">
              <div class="flex justify-between">
                <label class="mb-2 inline-block text-xs font-medium  text-gray-950" for="password">Password</label>
                <a href="auth-forgot-password-basic.html" class="cursor-pointer text-amber-500 no-underline hover:text-amber-500">
                  <small class=" ">Forgot Password?</small>
                </a>
              </div>
              <div class="relative flex w-full flex-wrap items-stretch">
                <input type="password" id="password" class="relative block flex-auto cursor-text appearance-none rounded-md border border-gray-400 bg--100 py-2 px-3 text-sm outline-none focus:border-amber-500 focus:bg-white focus:text-gray-600 focus:shadow" name="password" placeholder="············" />
              </div>
            </div>
            <div class="mb-4">
              <div class="block">
              
                <label class="inline-block" for="remember-me"> Remember Me </label>
              </div>
            </div>
            <div class="mb-4">
              <button class="grid w-full cursor-pointer select-none rounded-md border border-amber-500 bg-amber-500 py-2 px-5 text-center align-middle text-sm text-white shadow hover:border-yellow-600 hover:bg-yellow-500 hover:text-white focus:text-white focus:shadow-none" type="submit">Sign in</button>
            </div>
          </form>
  
          <p class="mb-4 text-center">
            New on NellitG?
            <a href="#" class="cursor-pointer text-amber-500 no-underline hover:text-yellow-500"> Create an account </a>
          </p>
        </div>
      </div>
      <!-- /Register -->
    </div>
  </div>
</template>