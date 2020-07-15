<template>
  <header style="background-color:#33298a" class="sticky top-0 grid grid-cols-6 grid-rows-1 items-center text-xl font-bold text-white">
    <div class="col-start-1 text-left" style="color:#0b9ad9">
      <Logo style="height:4rem" />
      <nuxt-link class="p-1 rounded text-2xl" style="font-family:serif" to="/">
        VEKXER
      </nuxt-link>
    </div>
    <div class="col-start-3 text-center mr-2">
      <nuxt-link class="p-1 rounded" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/about-me">
        TEAM
      </nuxt-link>
    </div>
    <div class="col-start-4">
      <nuxt-link class="p-1 rounded text-left mr-3" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/about-me">
        ABOUT ME
      </nuxt-link>
      <nuxt-link class="p-1 rounded" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/blogs">
        BLOGS
      </nuxt-link>
    </div>
    <div class="col-start-5">
      <nuxt-link class="p-1 rounded text-left ml-3" onmouseover="this.style.textDecoration=&quot;underline&quot;" onmouseout="this.style.textDecoration=&quot;none&quot;" to="/about-me">
        HIRE ME
      </nuxt-link>
    </div>
    <div class="col-start-9 mr-5">
      <nuxt-link class="p-1 rounded" style="background-color:#0b9ad9" to="/about-me">
        SIGN IN
      </nuxt-link>
    </div>
    <div class="col-start-10 mr-8">
      <nuxt-link class="p-1 rounded" style="background-color:#0b9ad9" to="/blogs">
        SIGN UP
      </nuxt-link>
    </div>
  </header>
</template>
