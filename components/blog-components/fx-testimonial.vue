<template>
  <div class="testimonial">
    <div class="memberName">
      <h2>
        {{ name }}
      </h2>
    </div>
    <div class="description">
      <h2>
        {{ description }}
      </h2>
    </div>
  </div>
</template>
<script>

export default {
  props: {
    name: String,
    description: String
  }
}
</script>
