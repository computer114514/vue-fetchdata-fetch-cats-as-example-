<script setup>
  import { ref, onMounted } from 'vue'

const list = ref([])          // 装数据的盒子
const loading = ref(true)     // 转圈提示
const error = ref(null)       // 错误提示

// 拿数据函数
async function getData() {
  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/posts')
    if (!res.ok) throw new Error('网络不对劲')
    list.value = await res.json()   // 把 JSON 塞进盒子，整个重置！json返回的就是盒子
  } catch (e) {
    error.value = e.message
  } finally {
    loading.value = false
  }
}

// 组件一 mounted 就执行
onMounted(getData)
</script>


<template>
  <p v-if="loading">转圈中…</p>
  <p v-else-if="error">{{ error }}</p>
  <ul v-else>
    <li v-for="item in list" :key="item.id">{{ item.title }}</li>
  </ul>
</template>

<style scoped></style>
