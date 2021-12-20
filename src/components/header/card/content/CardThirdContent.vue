<template>
    <!-- <Cards :text="text"> -->
    <Cards :text="texts.text">
    <!-- <Cards> -->
        <template #grid>
                <h1 class="text-gray-800 flex justify-start text-4xl dark:text-gray-500">Azriel</h1>
                <h2 class="text-gray-600 flex justify-start text-xl">Fakultas bisnis dan sastra</h2>
                <h4 class="text-gray-500 flex justify-end">Universitas negeri jakarta</h4>
                <div class="flex gap-3" v-for="(put, index) in texts" :key="index">
                    <label for="text">Txt input</label>
                    <input type="text" ref="insert" name="text" id="text" class="border-2 border-b-2 border-fuchsia-600" v-model="put.text">
                    <button class="my-auto p-1 bg-blue-600 rounded-md shadow-xl focus:bg-blue-700 hover:bg-blue-900" @click="deleteClick(index)">x</button>
                </div>
                    <!-- <label for="text">Txt input</label>
                    <input type="text" name="text" id="text" class="border-2 border-b-2 border-fuchsia-600" v-model="text"> -->
                <button class="mx-5 my-2 p-2 bg-blue-600 rounded-md shadow-xl focus:bg-blue-700 hover:bg-blue-900" @click="addClick()">Add input</button>
        </template>
    </Cards>
</template>#app

<script>
import Cards from '../Card.vue'
    
export default {
    components:{
        Cards
    },
    data() {
        return{
            texts:[
                {
                    text: ''
                }
            ]
            // text: ''
        }
    },
    methods: {
        // nambah element jangan lupa looping di element
        addClick(){
            let index = this.texts.text.length-1
            if (this.texts.text[index] != '') {
                this.texts.push({
                    text: ''
                })
                for (let index = 0; index < this.texts.text.length; index++) {
                    this.$refs.insert[index].readOnly = true
                }
            }
        },
        deleteClick(e){
            if (this.texts.length > 1) {
                this.texts.splice(e, 1)
                let index = this.texts.text.length-2
                this.$refs.insert[index].readOnly = false
            }
        }
    },
    computed:{
        selected() {
            return this.texts.map((form) => form.text)
        }
    },
    watch: {
        selected(e) {
            this.texts.text = e
        },
    }
}
</script>