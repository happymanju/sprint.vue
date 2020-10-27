<template>
  <div>
    <img
      :src="`data:image/*;base64,${selectedPhoto}`"
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
