<template>
  <article>
    <div class="overflow-hidden bg-cover h-screen" style="background-image: url(/img/league-of-legends.jpg)">
      <h1 class="text-3xl font-bold text-center font-semibold text-white">
        {{ blog.title }}
      </h1>
    </div>
    <div class="container mx-auto mt-3">
      <nuxt-content :document="blog" />
    </div>
  </article>
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
