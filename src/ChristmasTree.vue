<template>
  <div>
    <div v-for="(num, index) in size" :key="index" class="flex flex-row justify-center">
      <!-- This div is styled for the tree sections, but it's not complete -->
      <div
        v-for="(item, Iindex) in num"
        :key="Iindex"
        class="relative rounded-full w-16 h-16 -m-2 flex justify-center items-center"
        :class="{ 'bg-green': num % 2 === 0, 'bg-red-300': num % 2 !== 0 }"
      />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  size: {
    type: Number,
    default: 0,
  },
})
</script>
