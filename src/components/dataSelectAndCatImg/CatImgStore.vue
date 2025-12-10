<template>
    <div class="bigHeader">
        <el-button size="large">捕获新猫猫</el-button>
        <div class="Cat-Selector">
            <span>
                <img src="/public/cats/cat01.jpg" alt="err">
            </span>
        </div>
    </div>

    <fetchCat></fetchCat>
</template>

<script lang="js" setup>
    import fetchCat from './fetchCat2.vue';

    const list=ref([])
</script>

<style scoped>
    .el-button{
        margin:0 10px;
    }
    .bigHeader{
        align-items: center;
        display:flex;
        min-width:900px;
        width:90%;
        height:100px;
        margin:15px auto;
        background-color: #E3E5E7;
    }

    .Cat-Selector{
        background-color: #F6F7F8;
        height:80px;
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
</style>