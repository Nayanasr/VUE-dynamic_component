<template>
 <navbar-comp />
  <button @click="setSelectedComp('home-comp')">HOME</button>
  <button @click="setSelectedComp('login-comp')">LOGIN</button>

  <!-- <home-comp v-if="selectedComponent === 'home-comp'" />
  <login-comp v-if="selectedComponent === 'login-comp'" /> -->
   
  <keep-alive>
   <component :is="selectedComponent"> </component>
  </keep-alive>

</template>

<script>
import HomeComp from './components/HomeComp.vue'
import LoginComp from './components/LoginComp.vue'
import NavbarComp from './components/NavbarComp.vue'

export default {
  name: 'App',
  components: {
    NavbarComp,
    HomeComp,
    LoginComp
   
  },
  
  data(){
    return{
      selectedComponent: "home-comp",
    };
  },

  methods: {
    setSelectedComp(comp) {
      console.log("comp", comp);
      this.selectedComponent = comp;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


</style>
