<template>
  <ul class="imageGallery">
    <li v-for="(image, index) in images" :key="index">
      <fx-img :src="image.src" :alt="image.alt" />
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    images: { type: Array, default: null }
  }
}
</script>
