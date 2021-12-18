<template>
    <header class="bg-indigo-500 h-12 flex flex-wrap content-center bg-current dark:bg-white">
        <slot name="header-content"></slot>
        <slot></slot>
    </header>
</template>

<script>
export default {
    name:'bang'
}
</script>