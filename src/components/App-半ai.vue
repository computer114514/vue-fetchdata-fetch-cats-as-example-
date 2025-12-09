<script lang="js" setup>
    import {ref,onMounted} from "vue"

    const loading=ref(true);
    const error=ref(null)
    const information=ref([])

    async function fetchData(){
        try{
            const res=await fetch("https://jsonplaceholder.typicode.com/posts")
            //基本操作，抓取数据
            if(!res.ok){
                throw new Error ("网络不太对劲")
            }
            //边界判断：抓取失败
            // information.value.push(await res.json());
            information.value = await res.json()   // 把 JSON 塞进盒子,整个替换
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
    })
</script>

<template>
    <p v-if="loading">loading</p>
    <p v-else-if="error">{{ error }}</p>
       <ul v-else>
        <li v-for="item in information" :key="item.id">{{ item.title }}</li>
       </ul>

</template>

<style scoped>
</style>
