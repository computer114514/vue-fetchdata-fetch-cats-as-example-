<<<<<<< HEAD
<script lang="js" setup>
    import {ref} from "vue"
    import fetchcatFetch from "@/components/fetchDataAndCat/fetchcatFetch.vue"

    const count=ref(0)

    function updateIsNew(){
        count.value+=1;
    }
</script>

<template>
    <div class="bigbox">
        <div class="img"><fetchcatFetch :key="count"></fetchcatFetch></div>
        <el-button type="primary" size="large" @click="updateIsNew"> 获取随机小猫</el-button>
    </div>
</template>

<style scoped>
    *{
        padding:0;
        margin:0;
    }

    .img{
        margin:30px auto;
        width:500px;
        height:570px;
    }
    .bigbox{
        padding:10px;
        display:flex;
        flex-wrap: wrap;
        width:600px;
        height:700px;
        background-color: #F5F5F5;
    }
    .el-button{
        margin:0 230px;
    }
</style>
=======
<script lang="js" setup>
    import {ref} from "vue"
    import fetchcatFetch from "@/components/fetchDataAndCat/fetchcatFetch.vue"

    const count=ref(0)

    function updateIsNew(){
        count.value+=1;
    }
</script>

<template>
    <div class="bigbox">
        <div class="img"><fetchcatFetch :key="count"></fetchcatFetch></div>
        <el-button type="primary" size="large" @click="updateIsNew"> 获取随机小猫</el-button>
    </div>
</template>

<style scoped>
    *{
        padding:0;
        margin:0;
    }

    .img{
        margin:30px auto;
        width:500px;
        height:570px;
    }
    .bigbox{
        padding:10px;
        display:flex;
        flex-wrap: wrap;
        width:600px;
        height:700px;
        background-color: #F5F5F5;
    }
    .el-button{
        margin:0 230px;
    }
</style>
>>>>>>> 2168b27ac51c49cf8d50121e6f34e54e4956d72e
