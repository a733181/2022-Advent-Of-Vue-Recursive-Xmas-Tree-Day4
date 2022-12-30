<template>
  <div class="w-full h-full flex justify-center items-center flex-col">
    <ChristmasTree :size="size" />
    <input
      type="text"
      v-model="inputSize"
      class="mt-10 p-2 text-green placeholder:text-yellow-800 border border-green focus:border-blue-300 outline-none"
      :class="{ 'border-red-200': inputSize > 10 }"
      @change="chirstmasTreeSizeHandler"
      placeholder="請輸入聖誕樹高度"
    />
    <p v-if="inputSize > 10" class="text-red-300">聖誕樹高度最多為10</p>
    <p v-if="isNaN(Number(inputSize)) && inputSize !== ''">請輸入數字</p>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ChristmasTree from './ChristmasTree.vue'

const inputSize = ref('')
const size = ref()
const chirstmasTreeSizeHandler = () => {
  if (inputSize.value > 10) {
    size.value = 10
  } else if (!isNaN(Number(inputSize.value))) {
    size.value = Number(inputSize.value)
  } else {
    size.value = 0
  }
}
</script>
