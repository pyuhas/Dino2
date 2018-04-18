<template lang="html">
  <div class="theSkills">
    <li v-for='skill in skills' :key='skill'>{{skill}}</li>
  </div>
</template>

<script>
export default {
  name: 'theSkills',
  props: {
    skills: {
      type: Array,
      required: true
    }
  }
}
</script>
<style scoped>

#theSkills {
  list-style: none;
}
</style>
