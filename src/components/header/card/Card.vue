<template>
        <!-- <div class="max-w-md py-4 px-8 bg-white shadow-lg rounded-lg my-20">
            <div class="flex justify-center md:justify-end -mt-16">
                <img class="w-20 h-20 object-cover rounded-full border-2 border-indigo-500" src="https://images.unsplash.com/photo-1499714608240-22fc6ad53fb2?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=334&q=80">
            </div>
            <div>
                <h2 class="text-gray-800 text-3xl font-semibold">Design Tools</h2>
                <p class="mt-2 text-gray-600">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quae dolores deserunt ea doloremque natus error, rerum quas odio quaerat nam ex commodi hic, suscipit in a veritatis pariatur minus consequuntur!</p>
            </div>
            <div class="flex justify-end mt-4">
                <a href="#" class="text-xl font-medium text-indigo-500">John Doe</a>
            </div>
        </div> -->

        <div class="py-4 px-8 bg-gray-300 shadow-lg rounded-lg my-20 w-2/4 dark:bg-white ">
            <h3>it's a card</h3>
            <slot name="grid"></slot>
            <slot></slot>
        </div>
        <teleport to='body'>
            <error class="top-1/4 left-1/4" v-show="errors">
                <h2>you must input the text</h2>
                <!-- <button class="bg-blue-300 p-3 rounded-xl" @click="error()">Close</button> -->
            </error>
        </teleport>
        <!-- fungsi teleport untuk lempar ke tag -->
</template>

<script>
import error from '../../error/error.vue'
export default {
    name: 'Card',
    components:{
        error
    },
    // data() {
    //     return {
    //         error: true
    //     }
    // },
    inject:['errors'],
    props:['text'],
    watch: {
        text(){
            // let index = this.text.length-1
            // const her = this
            for (let index = 0; index < this.text.length; index++) {
                if (this.text[index] == '') {
                    this.errors = true
                    // console.log(this.text[index]);
                }
                else if (this.text[index] != '') {
                    this.errors = false
                }
                    // console.log(this.errors);
            }
        }
    },
    
}
</script>