<<<<<<< HEAD
<template>
    <div class="bigbox">
        <div class="img"><fetchcatFetch :key="count" @CatList="updateCatList1"></fetchcatFetch></div>
        <div class="buttons" style="display:flex;justify-content: space-around;width:100%;" tabindex="0" @keydown="OneKey">
            <el-button type="primary" size="large" @click="updateIsNew" > 随机小猫(→切换)</el-button>
            <el-button type="success" size="large" @click="updateCatList2">这个不错(Enter添加)</el-button>
            <!-- @click="updateCatList" -->
        </div>
    </div>
</template>

<script lang="js" setup>
    import {onMounted, ref,onUnmounted} from "vue"
    import fetchcatFetch from "./fetchcatFetch2.vue"

    const emit=defineEmits(["CatList"])
    const count=ref(0)
    const urlData=ref("");

    function OneKey(e){
        if(e.key==="Enter"){
            updateCatList2()
        }
        if(e.key==="ArrowRight"){
            updateIsNew()
        }
    }
    onMounted(()=>{
        window.addEventListener("keydown",OneKey)
    })
    onUnmounted(()=>{
        window.removeEventListener("keydown",OneKey)
    })


    function updateIsNew(){
        count.value+=1;
    }

    function updateCatList1(Data){
        console.log("更新了数据")
        urlData.value=Data.url;
    }

    function updateCatList2(){
        emit("CatList",urlData.value)
    }
</script>



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
</style>
=======
<template>
    <div class="bigbox">
        <div class="img"><fetchcatFetch :key="count" @CatList="updateCatList1"></fetchcatFetch></div>
        <div class="buttons" style="display:flex;justify-content: space-around;width:100%;" tabindex="0" @keydown="OneKey">
            <el-button type="primary" size="large" @click="updateIsNew" > 随机小猫(→切换)</el-button>
            <el-button type="success" size="large" @click="updateCatList2">这个不错(Enter添加)</el-button>
            <!-- @click="updateCatList" -->
        </div>
    </div>
</template>

<script lang="js" setup>
    import {onMounted, ref,onUnmounted} from "vue"
    import fetchcatFetch from "./fetchcatFetch2.vue"

    const emit=defineEmits(["CatList"])
    const count=ref(0)
    const urlData=ref("");

    function OneKey(e){
        if(e.key==="Enter"){
            updateCatList2()
        }
        if(e.key==="ArrowRight"){
            updateIsNew()
        }
    }
    onMounted(()=>{
        window.addEventListener("keydown",OneKey)
    })
    onUnmounted(()=>{
        window.removeEventListener("keydown",OneKey)
    })


    function updateIsNew(){
        count.value+=1;
    }

    function updateCatList1(Data){
        console.log("更新了数据")
        urlData.value=Data.url;
    }

    function updateCatList2(){
        emit("CatList",urlData.value)
    }
</script>



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
>>>>>>> 2168b27ac51c49cf8d50121e6f34e54e4956d72e
