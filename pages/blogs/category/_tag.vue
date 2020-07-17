<template>
  <div>
    <div class="text-center font-bold overflow-hidden bg-cover w-screen" style="background-color:#33298a">
      <h1 class="text-6xl text-black mb-4">
        {{ blog.slug }} Blog
      </h1>
    </div>
    <div class="text-center text-xl text-white" style="background-color:#0b9ad9">
      <nuxt-link class="mr-5" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/blogs">
        ALL
      </nuxt-link>
      <nuxt-link class="mr-5" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/blogs/Gaming">
        GAMING
      </nuxt-link>
      <nuxt-link class="mr-5" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/blogs/FPS">
        FPS
      </nuxt-link>
      <nuxt-link class="mr-5" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/blogs/MOBA">
        MOBA
      </nuxt-link>
      <nuxt-link class="mr-5" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/blogs/Strategy">
        STRATEGY
      </nuxt-link>
    </div>
    <div class="container mx-auto">
      <ul class="grid grid-cols-3 w-full gap-12 font-bold">
        <ul v-for="blog in blogs" :key="blog.tags.slug">
          <nuxt-link :to="`/blogs/${blog.slug}`">
            <div class="rounded overflow-hidden shadow-lg bg-white">
              <img class="w-full object-cover h-56" :src="blog.image" alt="BlogImage">
              <div class="px-6 py-4">
                <h2 class="font-bold text-2xl mb-2 mt-0">
                  {{ blog.title }}
                </h2>
                <div class="text-gray-700 text-base mb-2">
                  {{ blog.description }}
                </div>
                <div>
                  {{ blog.createdAt.slice(0,9) }}
                </div>
              </div>
              <div class="px-6 py-4 pt-0">
                <span v-for="(tag, index) in blog.tags" :key="index" class="inline-block bg-gray-300 rounded-full px-3 py-1 text-sm font-semibold text-gray-800 mr-2">
                  #{{ tag }}</span>
              </div>
            </div>
          </nuxt-link>
        </ul>
      </ul>
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
