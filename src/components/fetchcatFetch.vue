<script lang="js" setup>
    import {ref,onMounted} from "vue"

    const loading=ref(true);
    const error=ref(null)
    const information=ref({})
    async function fetchData(){
        try{
            const res=await fetch("https://api.thecatapi.com/v1/images/search")
            //基本操作，抓取数据
            if(!res.ok){
                throw new Error ("网络不太对劲")
            }
            //边界判断：抓取失败
            // information.value.push(await res.json());
            information.value = await res.json()   // 把 JSON 塞进盒子,整个替换
            console.log("test")
        }
        catch(e){
            error.value=e.message;
        }
        finally{
            loading.value=false;
        }
    }

    onMounted(()=>{
        fetchData();
            console.log(information.value.url)
    })
</script>

<template>
    <div v-if="loading" class="loading">loading</div>
    <p v-else-if="error">{{ error }}</p>
    <div v-else class="cat-container">
        <img :src="information[0].url"  alt="error" class="cat-img">
    </div>
</template>

<style scoped>
    .loading{
        font-size: 60px;
        line-height: 570px;
        text-align: center;
    }
    .cat-container{
        width:500px;
        height:570px;
        overflow: hidden;
    }
    img{
        width:500px;
        height:570px;
    }
    /* .cat-img{
        width:100%;
        height:auto;
        border-radius: 2%;
        box-shadow:1px 1px 1px black;
    } */
     /* 版本1:正常比例 */
         .cat-img{
        width:500px;
        height:570px;
        object-fit: cover;
        border-radius: 10%;
        /* box-shadow:1px 1px 1px black; */
    }
        /* 版本2：拉伸到大盒子 */
</style>
