﻿<template>
  <v-dialog
    v-model="$store.getters.getDialogVisible"
    max-width="600"
    @click:outside="$store.commit('hideDialog')"
  >
    <v-card>
      <v-card-title>{{ full_title }}</v-card-title>
      <v-card-text>
        <v-img :src="$store.getters.getCurrentPhoto.url" />
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "PhotoDialog",
  props: {},
  data: () => ({}),
  computed: {
    full_title() {
      return `Photo title - ${this.$store.getters.getCurrentPhoto.title}`;
    },
  },
};
</script>

<style scoped></style>
