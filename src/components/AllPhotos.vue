<template>
  <div>
    <img
      v-for="(photo, index) in photos[0]"
      :key="index"
      :src="`data:image/*;base64,${photo}`"
      alt="Couldn't load image"
      v-on:click="selectPhoto(photo)"
    />
  </div>
</template>

<script>
export default {
  name: "AllPhotos",
  props: [
    "photos",
  ],
  methods: {
    selectPhoto(photo) {
      this.$emit("update-SelectedPhoto", photo);
      console.log(photo);
    }
  }
};
</script>

<style></style>
