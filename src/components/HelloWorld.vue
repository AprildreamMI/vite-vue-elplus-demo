<template>
  <h1 class="tw-font-bold">{{ msg }}</h1>

  <div class="card">
    <el-button @click="mainStore.increment">count is {{ count }}</el-button>
    <el-select v-model="value" class="m-2" placeholder="Select">
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value"
      />
    </el-select>
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
import { ref } from 'vue';
import { useMainStore } from '../store/main'

defineProps({
  msg: String
})

const mainStore = useMainStore()
const { count } = storeToRefs(mainStore)

const value = ref('')

const options = [
  {
    value: 'Option1',
    label: 'Option1',
  },
  {
    value: 'Option2',
    label: 'Option2',
  },
  {
    value: 'Option3',
    label: 'Option3',
  },
  {
    value: 'Option4',
    label: 'Option4',
  },
  {
    value: 'Option5',
    label: 'Option5',
  },
]
  
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
