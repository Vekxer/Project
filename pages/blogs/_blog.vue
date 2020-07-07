<template>
  <div class="container">
    <article>
      <h1 class="titleBlog">
        {{ blog.title }}
      </h1>
      <nuxt-content :document="blog" />
    </article>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const blog = await $content('blogs', params.blog).fetch()
    // const blog = await $content('blogs').where({ title: 'params.blog' }).fetch()
    return { blog }
  }
}
</script>
