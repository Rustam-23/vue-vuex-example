<template>
  <v-app>
    <TheNavbar />
    <router-view></router-view>
  </v-app>
</template>

<script>
import TheNavbar from "@/components/TheNavbar";
export default {
  name: "App",
  components: { TheNavbar },
};
</script>
