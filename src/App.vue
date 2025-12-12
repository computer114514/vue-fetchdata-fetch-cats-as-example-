<script lang="js" setup>
    // import {fetchCat} from "./components/fetchCat.vue"
    //经典错误
    //{}是export多个，因此要{}包裹，fetchCat整个组件是默认导出
    import fetchCat2 from "./components/dataSelectAndCatImg/fetchCat2.vue";
    import fetchCat2Copy from "./components/dataSelectAndCatImg/fetchCat2Copy.vue";
    import CatImgStore from "./components/dataSelectAndCatImg/CatImgStore.vue";
</script>

<template>
    <!-- <fetchCat></fetchCat> -->
    <CatImgStore></CatImgStore>
</template>

<style scoped>
</style>
