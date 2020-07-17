<template>
  <ul class="team">
    <li v-for="(member, index) in teamMembers" :key="index">
      <fx-teamMember :name="member.name" :description="member.description" :title="member.title" :image="member.image" />
    </li>
  </ul>
</template>
<script>

export default {
  props: {
    teamMembers: { type: Array, default: null }
  }
}
</script>
