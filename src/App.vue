<template>
<div id="app">
  <theHeader></theHeader>
  <h2>Profiles</h2
      <ul id='dinos'>
    <theProfile v-for='dino in dinos' :dino='dino' :key='dino.name'></theProfile>
  </ul>
    <theSkills></theSkills>
    <theFooter></theFooter>
  </div>
</template>

<script>
import theHeader from './components/theHeader.vue'
import theProfile from './components/theProfile.vue'
import theSkills from './components/theSkills.vue'
import theFooter from './components/theFooter.vue'


export default {
  name: 'app',
  components: {
    theHeader,
    theProfile,
    theSkills,
    theFooter
  },
  data() {
    return {
      dinos:[]
    }
  },
  mounted() {
    fetch('./dinosaurs.json')
    .then(response=>response.json())
    .then(response=>{
      this.dinos=response
    })
  }
}

</script>

<style>

* {
  margin: 0;
  padding: 0;
}


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin: 0 30px 0 30px;
  padding: 0;
  font-family: sans-serif;
  color: #1B997A;
  display: grid;
  grid-template-rows: 15% 75% 10%;
}
</style>
