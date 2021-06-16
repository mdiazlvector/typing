<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <img alt="Pirate flag" src="./assets/Pirate.png">
    <custom-header 
        v-bind:frase="FRASE"
    ></custom-header>
    <custom-form 
        v-bind:frase-inicial="FRASE"
    ></custom-form>
  </div>
</template>

<script>
import CustomHeader from './components/CustomHeader.vue'
import CustomForm from './components/CustomForm.vue'
export default {
  name: 'App',
  data: function(){
     return {
        FRASE: 'En un lugar de la mancha'
      }
    },
  components: {
     CustomHeader,
     CustomForm
 
   },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
