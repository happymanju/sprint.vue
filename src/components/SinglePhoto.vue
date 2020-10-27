<template>
  <div>
    <img
      :src="`data:image/*;base64,${selectedphoto}`"
      alt="Couldn't load image"
    />
  </div>
</template>

<script>
export default {
  name: "SinglePhoto",
  props: ["selectedPhoto"]
};
</script>

<style></style>
