<template>
    <headers>
        <template v-slot:header-content>
            <h1 class="w-full">Belajar slots menggunakan tailwind</h1>
            <input type="checkbox" name="dark-mode" ref="dataValue" value="dark" @click="darkMode()">
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
    data() {
        return {
            dark : false
        }
    },
    methods: {
        darkMode(){
            // console.log(this.$refs.dataValue.value);
            this.dark = !this.dark
            // console.log(this.dark);
            this.$emit('darkMode', this.dark)
        }
    },
}
</script>