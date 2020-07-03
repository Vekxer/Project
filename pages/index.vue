<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        {{ home.title }}
      </h1>
      <nuxt-content :document="home" />
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
    const home = await $content('home').fetch()
    const blogs = await $content('blogs').fetch()
    return { home, blogs }
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

.title {
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
  color: #ffffff;
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
