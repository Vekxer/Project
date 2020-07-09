<template>
  <div class="container mx-auto">
    <article>
      <h1 class="w-full text-center text-3xl font-bold text-xl mb-2">
        {{ page.title }}
      </h1>
      <img class="object-container" style="width: 100%; height:35rem" :src="page.image" alt="BlogImage">
      <nuxt-content :document="page" />
    </article>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content, params }) {
    const page = await $content(params.slug).fetch()
    // const blog = await $content('blogs').where({ title: 'params.blog' }).fetch()
    return { page }
  }
}
</script>
