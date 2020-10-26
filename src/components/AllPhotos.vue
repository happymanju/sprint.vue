<template>
  <div>
    <img
      v-for="photo in photos"
      :key="photo"
      :src="`data:image/png;base64,${photo}`"
    alt="Couldn't load image" />
  </div>
</template>

<script>
export default {
  name: "AllPhotos",
  props: ["photos"]
};
</script>

<style></style>
