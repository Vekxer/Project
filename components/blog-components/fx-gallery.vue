<template>
  <div class="imageGallery">
    <div class="image">
      <fx-img :src="image1" alt="image1" />
    </div>
    <div class="image">
      <fx-img :src="image2" alt="image2" />
    </div>
    <div class="image">
      <fx-img :src="image3" alt="image3" />
    </div>
    <div class="image">
      <fx-img :src="image4" alt="image4" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    image1: Object,
    image2: Object,
    image3: Object,
    image4: Object
  }
}
</script>
