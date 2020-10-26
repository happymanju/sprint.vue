<template>
  <div class="uploadContainer">
    <input type="file" ref="input" @change="submitUploadFile($event)" />
    <!-- <button @click="() => submitUploadFile(this.ref.value)" type="submit">
      Upload
    </button> -->
  </div>
</template>

<script>
import { saveObject } from "../../utils/index";

export default {
  name: "Upload",
  methods: {
    submitUploadFile: async event => {
      await saveObject(event.target.value);
    }
  }
};
</script>

<style></style>
