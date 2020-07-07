<template>
  <div class="container">
    <div>
      <h1 class="title">
        This is the Blog page
      </h1>
      <p>Blogs you might enjoy:</p>
      <li v-for="blog in blogs" :key="blog.title">
        <nuxt-link :to="`/blogs/${blog.title}`">
          {{ blog.title }}
        </nuxt-link>
      </li>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const blogs = await $content('blogs').fetch()
    return { blogs }
  }
}
</script>
