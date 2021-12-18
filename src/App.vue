<template>
<div :class="dark ? 'dark bg-current h-screen' : ''" >

    <!-- <img alt="Vue logo" src="./assets/logo.png" class="mx-auto"> -->
    <headerContent @darkMode="darkButton"></headerContent>
    <!-- <headerSip @darkMode="darkButton"></headerSip> -->
    <cards></cards>
    </div>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import headerContent from './components/header/content/header-content.vue'
// import headerSip from './components/header/content/header-sip.vue'
import cards from './components/header/card/content/CardContent.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    headerContent,
    // headerSip,
    cards
  },
  data() {
    return {
      biodata:{
        name: "Nur arifin",
        prodi: "Informatika",
        kampus: "Universitas nasional"
      },
      dark: false
    }
  },
  provide(){
    return{
      biodatas: this.biodata
    }
  },
  methods: {
    darkButton(e){
      if (e == true) {
        this.dark = true
      }else{
        this.dark = false
      }
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
