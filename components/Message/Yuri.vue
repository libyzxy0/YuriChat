<template>
  <div class="flex justify-start">
      <div class="py-3 px-4 bg-slate-600 rounded-[25px] max-w-[80%] mx-4 text-gray-300 font-medium my-2 shadow">
        {{ text }} 
      </div>
  </div>
</template>
<script setup>
  defineProps({
    text: String
  })
</script>