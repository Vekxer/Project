<template>
  <article>
    <div class="overflow-hidden bg-cover h-screen" style="background-image: url(/img/league-of-legends.jpg)">
      <div class="text-6xl font-bold text-center items-center content-center text-white">
        {{ blog.title }}
      </div>
    </div>
    <div class="container max-w-screen-sm mx-auto mt-3">
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
