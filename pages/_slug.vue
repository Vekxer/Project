<template>
  <div class="container">
    <article>
      <h1 class="w-full text-center text-6xl font-bold text-xl mb-2">
        {{ page.title }}
      </h1>
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
