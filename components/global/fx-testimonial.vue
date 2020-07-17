<template>
  <div class="testimonial">
    <div class="memberImage">
      <fx-img :src="image" :alt="name" />
    </div>
    <div class="memberName">
      <h2>
        {{ name }}
      </h2>
    </div>
    <div class="memberTitle">
      <h2>
        {{ title }}
      </h2>
    </div>
    <div class="testimonialDescription">
      <p>
        {{ description }}
      </p>
    </div>
  </div>
</template>
<script>

export default {
  props: {
    name: { type: String, default: null },
    image: { type: String, default: null },
    description: { type: String, default: null },
    title: { type: String, default: null }
  }
}
</script>
