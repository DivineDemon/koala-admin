<template>
  <div
    class="flex flex-col md:flex-row justify-center items-center w-screen h-screen bg-gradient-to-r from-cyan-500 to-blue-500"
  >
    <div
      class="flex flex-col md:flex-row p-5 bg-white md:bg-transparent shadow-xl md:shadow-none rounded-lg"
    >
      <!-- Logo -->
      <div class="flex flex-row space-x-2 mr-5">
        <img
          src="../assets/img/loginlogo.png"
          alt=""
          class="w-12 h-12 md:w-24 md:h-24"
        />
        <span
          class="text-6xl md:text-8xl text-transparent bg-clip-text bg-gradient-to-r from-blue-500 to-cyan-500 font-bold md:text-white md:drop-shadow-xl"
          >KoalaSec</span
        >
      </div>
      <!-- Form -->
      <div
        class="flex flex-col space-y-5 text-gray-400 font-semibold md:bg-white md:p-5 md:rounded-md"
      >
        <fieldset class="border-t border-gray-300 mt-4">
          <legend class="mx-auto px-4 text-gray-500 text-sm">
            Please Login
          </legend>
        </fieldset>
        <div class="flex flex-col space-y-2">
          <label for="email">Email/Phone Number</label>
          <input
            class="text-cyan-600 border border-gray-600 focus:outline-cyan-500 p-2 rounded-md"
            type="text"
            name="email"
            placeholder="farhan@koalasec.com"
          />
        </div>
        <div class="flex flex-col space-y-2">
          <label for="password">Password</label>
          <input
            class="text-cyan-600 border border-gray-600 focus:outline-cyan-500 p-2 rounded-md"
            type="password"
            name="password"
            placeholder="********"
          />
        </div>
        <button
          class="flex flex-row justify-center space-x-2 text-white bg-gradient-to-r from-cyan-500 to-blue-500 p-2 rounded-md font-bold hover:shadow-lg"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15.75 9V5.25A2.25 2.25 0 0013.5 3h-6a2.25 2.25 0 00-2.25 2.25v13.5A2.25 2.25 0 007.5 21h6a2.25 2.25 0 002.25-2.25V15m3 0l3-3m0 0l-3-3m3 3H9"
            />
          </svg>

          <span>Login</span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LoginView",
};
</script>
