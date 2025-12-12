<<<<<<< HEAD
<template>
    <div class="bigHeader">
        <el-button size="large" @click="()=>{if(isFetch===false)isFetch=!isFetch;}">捕获新猫猫</el-button>
        <div class="Cat-Selector" :class="{fix:isfix}" ref="CatSelector">
            <span v-for="item in list" :key="item" class="Cat-Selector-list">
                <img :src="item" alt="err" @click="()=>{if(isFetch===true)isFetch=!isFetch;CatStoreUrl=item;}">
                <i class="iconfont icon-shanchu" @click="()=>{list=list.filter(itemTwo=>itemTwo!==item);fun()}"></i>
            </span>
        </div>
    </div>
    <fetchCat @CatList="updateCatList" v-if="isFetch"></fetchCat>
    <fetchCatCopy :CatStoreUrl="CatStoreUrl" v-if="!isFetch"></fetchCatCopy>
    <link rel="stylesheet" href="/public/图标/删除/iconfont.css">
</template>

<script lang="js" setup>
    import fetchCat from './fetchCat2.vue';
    import {nextTick,  ref} from "vue"
    import fetchCatCopy from './fetchCat2Copy.vue';
// import { linkEmits } from 'element-plus';
    const list=ref([])
    const CatSelector=ref(null)
    //这个同名的就是这个元素。
    const isFetch=ref(true)
    const CatStoreUrl=ref("")

    function updateCatList(url){
        console.log("is list value????",list.value[0])
        list.value=list.value.filter(item=>item!==url)
        list.value.push(url)
        fun()
    }

    const isfix=ref(false);
    async function fun(){
            await nextTick();
            const height=CatSelector.value.offsetHeight;
            isfix.value=height>165;
    }


    //nexTick代表等dom元素更新完成之后

</script>

<style scoped>
    .el-button{
        margin:0 10px;
    }
    .bigHeader{
        overflow-y: auto;
        align-items: center;
        display:flex;
        width:95%;
        height:auto;
        margin:15px auto;
        background-color: #E3E5E7;
    }
    .Cat-Selector{
        overflow-y: auto;
        background-color: #F6F7F8;
        height:105px;
        border:3px solid grey;
        border-radius:10px
    }
    .bigHeader .Cat-Selector span{
        
        /* span是行内块!!!!!!!!!!别想修改span的长宽，自然overflow也不行 */
        display: inline-block;
        height:60px;
        width:160px;
        overflow: hidden;
        border:2px solid #E3E5E7;
        margin:10px 20px;
        border-radius: 5%;
        img{
            width:100%;
            height:100%;
            object-fit: cover;
            border-radius: 5%;
        }
    }
    .fix{
        height:165px;
    }
    .Cat-Selector-list{
        height:auto;
        position: relative;
    }
    .Cat-Selector-list i{
        /* display: inline-block; */
        position: absolute; 
        top:18px;
        right:4px;

        opacity: 0;
        transition:opacity  0.1s ease-in;
    }
    .Cat-Selector-list:hover i{
        opacity: 1;
    }
    .Cat-Selector-list i:hover{
        color:red;
    }

=======
<template>
    <div class="bigHeader">
        <el-button size="large" @click="()=>{if(isFetch===false)isFetch=!isFetch;}">捕获新猫猫</el-button>
        <div class="Cat-Selector" :class="{fix:isfix}" ref="CatSelector">
            <span v-for="item in list" :key="item" class="Cat-Selector-list">
                <img :src="item" alt="err" @click="()=>{if(isFetch===true)isFetch=!isFetch;CatStoreUrl=item;}">
                <i class="iconfont icon-shanchu" @click="()=>{list=list.filter(itemTwo=>itemTwo!==item);fun()}"></i>
            </span>
        </div>
    </div>
    <fetchCat @CatList="updateCatList" v-if="isFetch"></fetchCat>
    <fetchCatCopy :CatStoreUrl="CatStoreUrl" v-if="!isFetch"></fetchCatCopy>
    <link rel="stylesheet" href="/public/图标/删除/iconfont.css">
</template>

<script lang="js" setup>
    import fetchCat from './fetchCat2.vue';
    import {nextTick, onMounted, ref} from "vue"
    import fetchCatCopy from './fetchCat2Copy.vue';
// import { linkEmits } from 'element-plus';
    const list=ref([])
    const CatSelector=ref(null)
    //这个同名的就是这个元素。
    const isFetch=ref(true)
    const CatStoreUrl=ref("")

    function updateCatList(url){
        console.log("is list value????",list.value[0])
        list.value=list.value.filter(item=>item!==url)
        list.value.push(url)
        fun()
    }

    const isfix=ref(false);
    async function fun(){
            await nextTick();
            const height=CatSelector.value.offsetHeight;
            isfix.value=height>165;
    }


    //nexTick代表等dom元素更新完成之后

</script>

<style scoped>
    .el-button{
        margin:0 10px;
    }
    .bigHeader{
        overflow-y: auto;
        align-items: center;
        display:flex;
        width:95%;
        height:auto;
        margin:15px auto;
        background-color: #E3E5E7;
    }
    .Cat-Selector{
        overflow-y: auto;
        background-color: #F6F7F8;
        height:105px;
        border:3px solid grey;
        border-radius:10px
    }
    .bigHeader .Cat-Selector span{
        
        /* span是行内块!!!!!!!!!!别想修改span的长宽，自然overflow也不行 */
        display: inline-block;
        height:60px;
        width:160px;
        overflow: hidden;
        border:2px solid #E3E5E7;
        margin:10px 20px;
        border-radius: 5%;
        img{
            width:100%;
            height:100%;
            object-fit: cover;
            border-radius: 5%;
        }
    }
    .fix{
        height:165px;
    }
    .Cat-Selector-list{
        height:auto;
        position: relative;
    }
    .Cat-Selector-list i{
        /* display: inline-block; */
        position: absolute; 
        top:18px;
        right:4px;

        opacity: 0;
        transition:opacity  0.1s ease-in;
    }
    .Cat-Selector-list:hover i{
        opacity: 1;
    }
    .Cat-Selector-list i:hover{
        color:red;
    }

>>>>>>> 2168b27ac51c49cf8d50121e6f34e54e4956d72e
</style>