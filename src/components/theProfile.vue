<template lang="html">
  <div id='theProfileCard'>
    <header class='theProfileHeader' v-on:click='skillsToggle = !skillsToggle'>
    <img :src='dino.image' alt=""/>
    <h1>{{dino.name}}</h1>
  </header>
  <section class='skills-container' :class="{ hidden : skillsToggle }">
    <h4>Skills</h4>
    <theSkills :skills='dino.skills'></theSkills>
  </section>

  </div>
</template>

<script>
import theSkills from './theSkills'

export default {
  name: 'theProfile',
  components: {
    theSkills
  },
  props: {
    dino: {
      type: Object,
      required: true
    }
  },
  data () {
    return {
      skillsToggle: true
    }
  }
}
</script>
<style scoped>

#theProfileCard {
  border-radius: 6px;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.3);
  padding: 10px;
  margin: 0 auto 0px auto;
  width: 500px;
}
.theProfileHeader {
  display: flex;
  flex-flow: row nowrap;
}
.theProfileHeader img {
  width: 100px;
  height: 100px;
  border: 1px solid darkgrey;
  margin: 0 10px 0 10px;
}
.hidden {
  display: none;
}

</style>
