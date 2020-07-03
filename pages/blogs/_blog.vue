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

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.titleBlog {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 85px;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
