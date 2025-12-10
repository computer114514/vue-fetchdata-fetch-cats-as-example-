<script lang="js" setup>
    import {ref} from "vue"
    import fetchcatFetch from "./fetchcatFetch2.vue"

    const count=ref(0)

    function updateIsNew(){
        count.value+=1;
    }
</script>

<template>
    <div class="bigbox">
        <div class="img"><fetchcatFetch :key="count"></fetchcatFetch></div>
        <div class="buttons" style="display:flex;justify-content: space-around;width:100%;">
            <el-button type="primary" size="large" @click="updateIsNew"> 获取随机小猫</el-button>
            <el-button type="success" size="large">这个不错</el-button>
        </div>
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
    /* .el-button{
        margin:0 230px;
    } */
</style>
