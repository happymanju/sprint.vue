<template>
  <div v-for="photo in photos">
    <img src="{{ photo }}" alt="Couldn't find" />
  </div>
</template>

<script>
export default {
  name: "AllPhotos"
};
</script>

<style></style>
