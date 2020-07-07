<template>
  <div>
    <h1>{{ blog.title }}</h1>
    <nuxt-content :document="blog" />
  </div>
</template>

<script>
export default {
  props: {
    blog: {
      default: () => {},
      type: Object
    }
  }
}
</script>
