<template>
  <header style="background-color:#33298a" class="sticky top-0 grid grid-cols-4 grid-rows-1 items-center text-2xl font-bold mb-2">
    <Logo style="height:5rem" />
    <div class="col-start-2">
      <nuxt-link to="/">
        Home
      </nuxt-link>
    </div>
    <div class="col-auto">
      <nuxt-link to="/about-me">
        About
      </nuxt-link>
    </div>
    <div class="col-auto">
      <nuxt-link to="/blogs">
        Blogs
      </nuxt-link>
    </div>
  </header>
</template>
