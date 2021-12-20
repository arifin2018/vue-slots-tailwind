<template >
    <cards>
        <template #grid>
                <h1 class="text-gray-800 flex justify-start text-4xl dark:text-gray-500">{{ biodatas.name }}</h1>
                <h2 class="text-gray-600 flex justify-start text-xl">{{ biodatas.prodi }}</h2>
                <h4 class="text-gray-500 flex justify-end">{{ biodatas.kampus }}</h4>
        </template>
        
    </cards>
</template>

<script>
import cards from '../Card.vue'
export default {
    name: 'CardContent',
    components:{
        cards
    },
    inject:['biodatas'],
}
</script>