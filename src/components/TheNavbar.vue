<template>
  <v-container fluid>
    <v-app-bar color="orange" dark>
      <v-spacer />
      <v-btn outlined class="ml-3">
        <router-link to="/">Home</router-link>
      </v-btn>
      <v-btn outlined class="ml-3">
        <router-link to="/zone">Zone</router-link>
      </v-btn>
    </v-app-bar>
  </v-container>
</template>

<script>
export default {
  name: "TheNavbar",
};
</script>

<style scoped></style>
