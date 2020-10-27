<template>
  <div class="all-photos">
    <button v-on:click="allPhotosView()">All Photos</button>
    <upload />
  </div>
</template>

<script>
import Upload from "./Upload";

export default {
  name: "Navbar",
  components: {
    upload: Upload
  },
  props: ["allPhotosView"]
};
</script>

<style>
.all-photos {
  background-color: #444444;
  color: white;
  height: 50px;
  margin: auto;
  max-width: 650px;
}
</style>
