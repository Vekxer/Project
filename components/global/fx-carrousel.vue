<template>
  <ul class="imageCarrousel">
    <li v-for="(image, index) in images" :key="index">
      <fx-img :src="images.src" :alt="images.src" />
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
