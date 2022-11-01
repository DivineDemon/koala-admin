<template>
  <div
    class="home w-screen h-screen bg-gradient-to-r from-cyan-500 to-blue-500"
  >
    <NavBar />
  </div>
</template>

<script>
import NavBar from "@/components/NavBar.vue";

export default {
  name: "HomeView",
  components: {
    NavBar,
  },
};
</script>
