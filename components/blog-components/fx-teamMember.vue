<template>
  <div class="teamMember">
    <div class="fx-img">
      <fx-img :src="image" alt="memberImage" />
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
    <div class="memberDescription">
      <p>
        {{ description }}
      </p>
    </div>
  </div>
</template>
<script>

export default {
  props: {
    name: String,
    image: Object,
    description: String,
    title: String
  }
}
</script>
