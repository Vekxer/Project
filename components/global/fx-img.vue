<template>
  <img :src="src" :alt="alt">
</template>

<script>
export default {
  props: {
    src: { type: String, default: null },
    alt: { type: String, default: null }
  }
}
</script>
