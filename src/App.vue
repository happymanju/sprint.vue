<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>{{ title }}</h1>
    <navbar :allPhotos="allPhotos" />
    <div class="allPhotos">
      <allPhotos :photos="photos"/>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import AllPhotos from "./components/AllPhotos";
// import SinglePhoto from "./components/SinglePhoto";
import { listObjects, getSingleObject } from "../utils/index";

export default {
  name: "App",
  components: {
    navbar: Navbar,
    allPhotos: AllPhotos
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
  }
};
</script>

<style>
#app {
  text-align: center;
}
</style>
