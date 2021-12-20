<template>
    <headers>
            <h1 class="w-full">Belajar slots menggunakan tailwind</h1>
            <input type="checkbox" @click="darkMode()" checked>
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
    // data() {
    //     return {
    //         dark : false
    //     }
    // },
    methods: {
        darkMode(){
            // console.log(this.$refs.dataValue.value);
            // this.dark = !this.dark
            console.log(this.dark);
            // console.log(this.dark);
            // this.$emit('darkMode', this.dark)
        }
    },
}
</script>