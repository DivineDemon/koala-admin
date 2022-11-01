<template>
  <div class="w-screen h-screen bg-gradient-to-r from-cyan-500 to-blue-500">
    <NavBar />
    <div class="flex align-center items-center justify-center">
      <GuardTable />
    </div>
  </div>
</template>

<script>
import NavBar from "@/components/NavBar.vue";
import GuardTable from "@/components/GuardTable.vue";

export default {
  name: "HomeView",
  components: {
    NavBar,
    GuardTable,
  },
};
</script>
