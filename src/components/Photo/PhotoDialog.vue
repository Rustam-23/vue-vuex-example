<template>
  <v-dialog
      v-model="dialogVisible"
      max-width="600"
  >
    <v-card>
      <v-card-title>{{ photo.title }}</v-card-title>
      <v-card-text>
        <v-img :src="photo.img"/>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "PhotoDialog",
  props: {
    photo: {
      type: Object,
      required: true,
    },
    dialogVisible: {
      type: Boolean,
      default: false,
    }
  },
  data: () => ({})
}
</script>

<style scoped>

</style>