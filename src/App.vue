<script lang="js" setup>
    // import {fetchCat} from "./components/fetchCat.vue"
    //经典错误
    //{}是export多个，因此要{}包裹，fetchCat整个组件是默认导出
    import fetchCat from "./components/fetchCat.vue"
    import fetchcatFetch from "./components/fetchcatFetch.vue"

</script>

<template>
    <fetchCat></fetchCat>
</template>

<style scoped>
</style>
