<template>
    <header class="bg-indigo-500 h-12 flex flex-wrap content-center bg-current dark:bg-gray-300">
        <slot name="HeaderContent">
            <h3>testing</h3>
        </slot>
        <slot name="default"></slot>
        <slot ></slot>
    </header>
</template>

<script>
export default {
    name:'bang',
    // mounted() {
    //     console.log(this.$slots.HeaderContent);
    // },
}
</script>