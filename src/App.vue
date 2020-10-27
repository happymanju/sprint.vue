<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>{{ title }}</h1>
    <navbar :allPhotosView="allPhotosView" />
    <div class="Photos">
      <allPhotos v-bind:photos="photos" v-bind:selectedphoto="selectedphoto" />
      <singlePhoto v-bind:photos="photos" />
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import AllPhotos from "./components/AllPhotos";
import SinglePhoto from "./components/SinglePhoto";
import { listObjects, getSingleObject } from "../utils/index";

export default {
  name: "App",
  components: {
    navbar: Navbar,
    allPhotos: AllPhotos,
    singlePhoto: SinglePhoto
  },
  data: () => ({
    title: "Photo Upload App",
    currentView: "allPhotos",
    photos: [],
    selectedPhoto: ""
  }),
  methods: {
    allPhotosView() {
      this.currentView = "allPhotos";
    },
    async fetchAllPhotos() {
      const arrayOfObjects = await listObjects();
      let resolved = arrayOfObjects.map(obj => obj.Key);
      let resolvedTen = resolved.splice(0, 10);
      let promiseOfKeys = resolvedTen.map(
        async key => await getSingleObject(key)
      );
      Promise.all(promiseOfKeys).then(base64String => {
        this.photos.push(base64String);
        console.log(this.photos);
      });
    }
  },
  created() {
    this.fetchAllPhotos();
  }
};
</script>

<style>
#app {
  text-align: center;
}
</style>
