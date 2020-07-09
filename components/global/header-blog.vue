<template>
  <header style="background-color:#33298a" class="sticky top-0 grid grid-cols-4 grid-rows-1 items-center text-2xl font-bold">
    <Logo style="height:4rem" />
    <div class="col-start-2" style="color:white">
      <nuxt-link class="p-1 rounded" style="background-color:#0b9ad9" to="/">
        HOME
      </nuxt-link>
    </div>
    <div class="col-auto" style="color:white">
      <nuxt-link class="p-1 rounded" style="background-color:#0b9ad9" to="/about-me">
        ABOUT ME
      </nuxt-link>
    </div>
    <div class="col-auto" style="color:white">
      <nuxt-link class="p-1 rounded" style="background-color:#0b9ad9" to="/blogs">
        BLOGS
      </nuxt-link>
    </div>
  </header>
</template>
