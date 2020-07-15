<template>
  <div class="container mx-auto">
    <div class="w-full text-center text-3xl font-bold mb-2">
      <Logo />
      <div class="text-6xl">
        {{ home.title }}
      </div>
      <h2>
        Here are the recent blogs:
      </h2>
      <div class="blogsHeader">
        {{ blogs.tags }}
      </div>
    </div>
    <ul class="grid grid-cols-3 w-full gap-12 font-bold">
      <ul v-for="blog in blogs" :key="blog.slug">
        <nuxt-link :to="`/blogs/${blog.slug}`">
          <div class="rounded overflow-hidden shadow-lg bg-white">
            <img class="w-full object-cover h-56" :src="blog.image" alt="BlogImage">
            <div class="px-6 py-4">
              <h2 class="font-bold mb-2 mt-0">
                {{ blog.title }}
              </h2>
              <div class="text-gray-700 text-base mb-2">
                {{ blog.description }}
              </div>
              <div>
                {{ blog.createdAt.slice(0,9) }}
              </div>
              <div class="px-0 py-0 pt-4">
                <span v-for="(tag, index) in blog.tags" :key="index" class="inline-block bg-gray-300 rounded-full px-2 py-1 text-sm font-semibold text-gray-800 mr-2">
                  #{{ tag }}</span>
              </div>
            </div>
          </div>
        </nuxt-link>
      </ul>
    </ul>
  </div>
</template>

<script>
export default {
  async asyncData ({ $content }) {
    const home = await $content('home').fetch()
    const blogs = await $content('blogs').sortBy('DateCreated').limit(3).fetch()
    return { home, blogs }
  }
}
</script>
