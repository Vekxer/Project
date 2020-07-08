<template>
  <div class="container mx-auto">
    <div class="w-full text-center text-3xl font-bold mb-2">
      <Logo />
      <h1 class="text-6xl">
        This is the Blog page
      </h1>
      <h1 class="text-xl">
        Blogs you might enjoy:
      </h1>
    </div>
    <ul class="grid grid-cols-3 w-full gap-12">
      <li v-for="blog in blogs" :key="blog.slug">
        <nuxt-link :to="`/blogs/${blog.slug}`">
          <div class="rounded overflow-hidden shadow-lg bg-white">
            <img class="w-full object-cover h-56" :src="blog.image" alt="BlogImage">
            <div class="px-6 py-4">
              <div class="font-bold text-xl mb-2">
                {{ blog.title }}
              </div>
              <p class="text-gray-700 text-base">
                {{ blog.description }}
              </p>
            </div>
            <div class="px-6 py-4">
              <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#{{ blog.tag1 }}</span>
              <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#{{ blog.tag2 }}</span>
              <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700">#{{ blog.tag3 }}</span>
            </div>
          </div>
        </nuxt-link>
      </li>
    </ul>
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
