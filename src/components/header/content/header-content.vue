<template>
    <headers>
        <template #HeaderContent>
            <h1 class="w-full">Belajar slots menggunakan tailwind</h1>
            <div class="flex w-full">
                <div class="flex-initial mx-auto">
                    <input type="checkbox" id="darkmode" @click="darkMode()" :checked="dark">
                    <label for="darkmode">DarkMode</label>
                </div>
            </div>
        </template>
        <!-- default slot -->
        <template>
            <div class="w-screen">
                <h3>tailwinds css</h3>
            </div>
        </template>
    </headers>
</template>

<script>
import headers from '../bang'
export default {
    name: 'header-content',
    components:{
        headers
    },
    inject:['dark'],
    methods: {
        darkMode(){
            this.dark = !this.dark
            // console.log(this.dark);
            this.$emit('darkMode', this.dark)
        }
    },
    // // mounted() {
    // //     let getDarkModeLocalStorage = JSON.parse(localStorage.getItem('darkMode'))
    // //     if (getDarkModeLocalStorage != null) {
    // //     this.dark = getDarkModeLocalStorage
    // //     }
    // // },
    mounted() {
        // const getDarkModeLocalStorage = JSON.parse(localStorage.getItem('darkMode'))
        // if (getDarkModeLocalStorage != null) {
        //     this.dark = getDarkModeLocalStorage
        // }
        // console.log(this.dark, 'tes');
    },
}
</script>