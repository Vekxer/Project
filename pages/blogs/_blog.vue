<template>
  <div class="container mx-auto">
    <article>
      <h1 class="text-3xl font-bold mb-2 text-center">
        {{ blog.title }}
      </h1>
      <img class="object-container" style="width: 100%; height:35rem" :src="blog.image" alt="BlogImage">
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
