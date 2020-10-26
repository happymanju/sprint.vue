<template>
  <div class="all-photos">
    <p v-on:click="submitUploadFile()">All Photos</p>
    <upload />
  </div>
</template>

<script>
import Upload from "./Upload";
import { saveObject } from "../../utils/index";

export default {
  name: "Navbar",
  components: {
    upload: Upload
  },
  props: ["allPhotosView"],
  methods:{
    submitUploadFile = async file => {
    await saveObject(file);
    }
  },
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
