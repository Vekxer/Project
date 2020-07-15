<template>
  <article>
    <div class="overflow-hidden bg-cover h-screen" style="background-image: url(/img/league-of-legends.jpg)">
      <h1 class="text-6xl font-bold text-center text-white">
        {{ page.title }}
      </h1>
    </div>
    <div class="container max-w-screen-sm mx-auto mt-3">
      <nuxt-content :document="page" />
    </div>
  </article>
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
