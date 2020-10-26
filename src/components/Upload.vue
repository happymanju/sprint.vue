<template>
  <div class="uploadContainer">
    <input type="file" ref="input" />
    <button @click="e => saveObject(this.ref.value)" type="submit">
      Upload
    </button>
  </div>
</template>

<script>
import { saveObject } from "../../utils/index";

export default {
  name: "Upload",
  methods: {
    onFileSelected(event) {
      console.log("Hello")
    }
  }
};
</script>

<style></style>
