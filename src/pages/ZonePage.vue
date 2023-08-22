<template>
  <v-container>
    <PhotoForm @addPhoto="addPhoto" />
    <v-row>
      <ThePhoto v-for="photo in photos" :key="photo.id" v-bind:photo="photo" />
    </v-row>
    <PhotoDialog :photo="currentPhoto" : dialogVisible="dialogVisible"/>
  </v-container>
</template>

<script>
import ThePhoto from "@/components/Photo/ThePhoto";
import PhotoForm from "@/components/Photo/PhotoForm";
import PhotoDialog from "@/components/Photo/PhotoDialog";

export default {
  name: "ZonePage",
  components: { ThePhoto, PhotoForm, PhotoDialog },
  data: () => ({
    photos: [],
    currentPhoto: null,
    dialogVisible: false,
  }),
  mounted() {
    this.fetchPhoto();
  },
  methods: {
    fetchPhoto() {
      this.axios
        .get("https://jsonplaceholder.typicode.com/albums/1/photos?_limit=10")
        .then((res) => (this.photos = res.data));
    },
    addPhoto(photo) {
      this.photos.push(photo);
    },
    openPhoto(photo) {
      this.currentPhoto = photo
      this.dialogVisible = true
    },
  },
};
</script>

<style scoped></style>
