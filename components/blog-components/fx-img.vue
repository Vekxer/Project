<template>
  <div class="image">
    <img :src="src" :alt="alt">
  </div>
</template>

<script>
export default {
  props: {
    src: String,
    alt: String
  }
}
</script>
