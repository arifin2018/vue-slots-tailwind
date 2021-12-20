<template>
        <ul>
            <li v-for="goal in goals" :key="goal" class="text-gray-600 dark:text-white">
                <!-- {{ goal }} -->
                <slot :goal="goal" tesProps="..."></slot>
            </li>
        </ul>
</template>

<script>
export default {
    data() {
        return {
            goals:['testing', 'vuejs', 'bissmilah-learn vue']
        }
    },
}
</script>