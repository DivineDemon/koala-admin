<template>
  <div class="flex flex-col bg-white">
    <!-- Non-Responsive -->
    <nav class="flex flex-row justify-between items-center p-5 shadow-md">
      <!-- Logo -->
      <router-link class="flex flex-row space-x-2 items-center" to="/">
        <img src="../assets/img/loginlogo.png" alt="" class="flex w-10" />
        <span class="font-bold text-blue-500 text-4xl">KoalaSec</span>
      </router-link>
      <!-- Nav Items -->
      <div class="hidden md:flex items-center">
        <ul class="flex flex-row space-x-[75px] items-center">
          <li
            class="font-bold cursor-pointer flex flex-row"
            :class="{
              'text-blue-500 border-2 border-blue-500 rounded-md p-2':
                active === 'dashboard',
            }"
            @click="setActive('dashboard')"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6 mr-3"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M2.25 12l8.954-8.955c.44-.439 1.152-.439 1.591 0L21.75 12M4.5 9.75v10.125c0 .621.504 1.125 1.125 1.125H9.75v-4.875c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21h4.125c.621 0 1.125-.504 1.125-1.125V9.75M8.25 21h8.25"
              />
            </svg>

            Dashboard
          </li>
          <li
            class="font-bold cursor-pointer flex flex-row"
            :class="{
              'text-blue-500 border-2 border-blue-500 rounded-md p-2':
                active === 'companies',
            }"
            @click="setActive('companies')"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6 mr-3"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M2.25 21h19.5m-18-18v18m10.5-18v18m6-13.5V21M6.75 6.75h.75m-.75 3h.75m-.75 3h.75m3-6h.75m-.75 3h.75m-.75 3h.75M6.75 21v-3.375c0-.621.504-1.125 1.125-1.125h2.25c.621 0 1.125.504 1.125 1.125V21M3 3h12m-.75 4.5H21m-3.75 3.75h.008v.008h-.008v-.008zm0 3h.008v.008h-.008v-.008zm0 3h.008v.008h-.008v-.008z"
              />
            </svg>

            Companies
          </li>
          <li
            class="font-bold cursor-pointer flex flex-row"
            :class="{
              'text-blue-500 border-2 border-blue-500 rounded-md p-2':
                active === 'guards',
            }"
            @click="setActive('guards')"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6 mr-3"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M18 18.72a9.094 9.094 0 003.741-.479 3 3 0 00-4.682-2.72m.94 3.198l.001.031c0 .225-.012.447-.037.666A11.944 11.944 0 0112 21c-2.17 0-4.207-.576-5.963-1.584A6.062 6.062 0 016 18.719m12 0a5.971 5.971 0 00-.941-3.197m0 0A5.995 5.995 0 0012 12.75a5.995 5.995 0 00-5.058 2.772m0 0a3 3 0 00-4.681 2.72 8.986 8.986 0 003.74.477m.94-3.197a5.971 5.971 0 00-.94 3.197M15 6.75a3 3 0 11-6 0 3 3 0 016 0zm6 3a2.25 2.25 0 11-4.5 0 2.25 2.25 0 014.5 0zm-13.5 0a2.25 2.25 0 11-4.5 0 2.25 2.25 0 014.5 0z"
              />
            </svg>

            Guards
          </li>
          <li
            class="font-bold cursor-pointer flex flex-row"
            :class="{
              'text-blue-500 border-2 border-blue-500 rounded-md p-2':
                active === 'jobs',
            }"
            @click="setActive('jobs')"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-6 h-6 mr-3"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M20.25 14.15v4.25c0 1.094-.787 2.036-1.872 2.18-2.087.277-4.216.42-6.378.42s-4.291-.143-6.378-.42c-1.085-.144-1.872-1.086-1.872-2.18v-4.25m16.5 0a2.18 2.18 0 00.75-1.661V8.706c0-1.081-.768-2.015-1.837-2.175a48.114 48.114 0 00-3.413-.387m4.5 8.006c-.194.165-.42.295-.673.38A23.978 23.978 0 0112 15.75c-2.648 0-5.195-.429-7.577-1.22a2.016 2.016 0 01-.673-.38m0 0A2.18 2.18 0 013 12.489V8.706c0-1.081.768-2.015 1.837-2.175a48.111 48.111 0 013.413-.387m7.5 0V5.25A2.25 2.25 0 0013.5 3h-3a2.25 2.25 0 00-2.25 2.25v.894m7.5 0a48.667 48.667 0 00-7.5 0M12 12.75h.008v.008H12v-.008z"
              />
            </svg>

            Jobs
          </li>
        </ul>
      </div>
      <!-- Logout -->
      <div class="hidden md:flex">
        <button
          class="flex flex-row space-x-2 bg-red-500 text-white font-bold p-2 rounded-md"
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
              d="M15.75 9V5.25A2.25 2.25 0 0013.5 3h-6a2.25 2.25 0 00-2.25 2.25v13.5A2.25 2.25 0 007.5 21h6a2.25 2.25 0 002.25-2.25V15M12 9l-3 3m0 0l3 3m-3-3h12.75"
            />
          </svg>
          <span>Logout</span>
        </button>
      </div>
      <!-- Responsive Menu Toggle -->
      <button class="flex md:hidden text-blue-500" @click="toggleNavMenu">
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
            d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
          />
        </svg>
      </button>
    </nav>
    <!-- Responsive -->
    <div class="flex flex-col">
      <!-- Nav Items -->
      <div v-if="isOpen" class="p-5 z-50 shadow-md">
        <ul class="flex flex-col space-y-3">
          <li
            class="font-bold cursor-pointer"
            :class="{
              'text-blue-500 border-b-2 border-blue-500':
                active === 'dashboard',
            }"
            @click="setActive('dashboard')"
          >
            <router-link to="/">Dashboard</router-link>
          </li>
          <li
            class="font-bold cursor-pointer"
            :class="{
              'text-blue-500 border-b-2 border-blue-500':
                active === 'companies',
            }"
            @click="setActive('companies')"
          >
            Companies
          </li>
          <li
            class="font-bold cursor-pointer"
            :class="{
              'text-blue-500 border-b-2 border-blue-500': active === 'guards',
            }"
            @click="setActive('guards')"
          >
            Guards
          </li>
          <li
            class="font-bold cursor-pointer"
            :class="{
              'text-blue-500 border-b-2 border-blue-500': active === 'jobs',
            }"
            @click="setActive('jobs')"
          >
            Jobs
          </li>
          <li class="font-bold cursor-pointer text-red-500">
            <router-link to="/login">Logout</router-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      active: "dashboard",
      isOpen: false,
    };
  },
  methods: {
    setActive(item) {
      this.active = item;
    },
    toggleNavMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>
