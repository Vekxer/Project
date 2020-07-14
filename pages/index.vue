<template>
  <div class="container mx-auto">
    <div class="w-full text-center text-3xl font-bold mb-2">
      <Logo />
      <h1 class="text-6xl">
        {{ home.title }}
      </h1>
      <h1 class="text-xl">
        Here are the recent blogs:
      </h1>
      <div class="blogsHeader">
        {{ blogs.tags }}
      </div>
    </div>
    <ul class="grid grid-cols-3 w-full gap-12 font-bold">
      <li v-for="blog in blogs" :key="blog.slug">
        <nuxt-link :to="`/blogs/${blog.slug}`">
          <div class="rounded overflow-hidden shadow-lg bg-white">
            <img class="w-full object-cover h-56" :src="blog.image" alt="BlogImage">
            <div class="px-6 py-4">
              <div class="font-bold text-2xl mb-2">
                {{ blog.title }}
              </div>
              <p class="text-gray-700 text-base">
                {{ blog.description }}
              </p>
              <h1>
                {{ blog.createdAt[0] }}{{ blog.createdAt[1] }}{{ blog.createdAt[2] }}{{ blog.createdAt[3] }}{{ blog.createdAt[4] }}{{ blog.createdAt[5] }}{{ blog.createdAt[6] }}{{ blog.createdAt[7] }}{{ blog.createdAt[8] }}{{ blog.createdAt[9] }}
              </h1>
            </div>
            <div class="px-6 py-4">
              <span v-for="(tag, index) in blog.tags" :key="index" class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">
                #{{ tag }}</span>
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
    const home = await $content('home').fetch()
    const blogs = await $content('blogs').sortBy('DateCreated').limit(3).fetch()
    return { home, blogs }
  }
}
</script>
