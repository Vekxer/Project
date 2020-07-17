<template>
  <div class="team">
    <ul v-for="name in names" :key="name">
      <fx-teamMember :name="names[0]" :description="descriptions[0]" :title="titles[0]" :image="images[0]" />
    </ul>
  </div>
</template>
<script>

export default {
  props: {
    names: Array,
    descriptions: Array,
    titles: Array,
    images: Array
  }
}
</script>
