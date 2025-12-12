<<<<<<< HEAD
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
=======
<script lang="js" setup>
    // import {fetchCat} from "./components/fetchCat.vue"
    //经典错误
    //{}是export多个，因此要{}包裹，fetchCat整个组件是默认导出
    import fetchCat from "./components/fetchDataAndCat/fetchCat.vue"
    import fetchcatFetch from "./components/fetchDataAndCat/fetchcatFetch.vue"
    
    import CatImgStore from "./components/dataSelectAndCatImg/CatImgStore.vue";
</script>

<template>
    <!-- <fetchCat></fetchCat> -->
    <CatImgStore></CatImgStore>
</template>

<style scoped>
</style>
>>>>>>> 2168b27ac51c49cf8d50121e6f34e54e4956d72e
