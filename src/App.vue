<template>
  <div :class="dark == true ? 'dark bg-current h-screen' : ''" >

    <headerContent @darkMode="darkButton"></headerContent>
    <div class="flex gap-4">
      <button class="mx-5 p-2 bg-red-400 rounded-md shadow-xl focus:bg-red-700 hover:bg-red-500" @click="clickElement('cards')">Card first</button>
      <button class="mx-5 p-2 bg-red-400 rounded-md shadow-xl focus:bg-red-700 hover:bg-red-500" @click="clickElement('card-third')">Second Card</button>
    </div>
    <div class="flex flex-row gap-4 pl-3">
      <!-- <cards class="w-3/12" v-show="selectElement == 'cards'"></cards> -->
      <!-- <card-seconds>
        <template #default="slotProps">
          <h2>{{ slotProps.goal }}</h2>
          <h3>{{ slotProps.tesProps }}</h3>
        </template>
      </card-seconds> -->
      <!-- <card-third class="w-3/12" v-show="selectElement == 'card-third'"></card-third> -->
      <keep-alive>
        <component :is="selectElement ? selectElement : 'cards'"></component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import headerContent from './components/header/content/header-content.vue'
// import headerSip from './components/header/content/header-sip.vue'
import cards from './components/header/card/content/CardContent.vue'
// import cardSeconds from './components/header/card/content/CardSecondContent.vue'
import cardThird from './components/header/card/content/CardThirdContent.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    headerContent,
    // headerSip,
    cards,
    // cardSeconds,
    cardThird
  },
  data() {
    return {
      biodata:{
        name: "Nur arifin",
        prodi: "Informatika",
        kampus: "Universitas nasional"
      },
      selectElement: 'cards',
      dark: localStorage.getItem('darkMode') ? JSON.parse(localStorage.getItem('darkMode')) : false,
      error: false
    }
  },
  // async beforeMount() {
  //     const getDarkModeLocalStorage = await JSON.parse(localStorage.getItem('darkMode'))
  //     if (getDarkModeLocalStorage != null) {
  //       this.dark = getDarkModeLocalStorage
  //     }
  //     console.log(this.dark + 'ok');
  // },
  provide(){
    return{
      biodatas: this.biodata,
      dark: this.dark,
      errors: this.clickElement()
    }
  },
  methods: {
    darkButton(e){
      if (e == true) {
        this.dark = true
        localStorage.setItem('darkMode', JSON.stringify(this.dark))
      }else{
        this.dark = false
        localStorage.setItem('darkMode', JSON.stringify(this.dark))
      }
    },
    clickElement(e){
      this.selectElement = e;
      if (this.selectElement == 'cards') {
          return this.error = false
        } else if (this.selectElement == 'card-third') {
          return this.error = true
        }
      // console.log(this.selectElement);
    },
  },
  // mounted() {
  //   console.log(this.selectElement);
  // }
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
