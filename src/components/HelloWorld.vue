<template>
  <h1 class="tw-font-bold">{{ msg }}</h1>

  <div class="card">
    <el-button @click="mainStore.increment">count is {{ count }}</el-button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Install
    <a href="https://github.com/johnsoncodehk/volar" target="_blank">Volar</a>
    in your IDE for a better DX
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<script setup>
import { storeToRefs } from 'pinia';
import { useMainStore } from '../store/main'

defineProps({
  msg: String
})

const mainStore = useMainStore()
const { count } = storeToRefs(mainStore)
  
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
