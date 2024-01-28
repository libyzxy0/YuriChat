<template>
  <div class="flex justify-end">
      <div class="py-3 px-4 bg-green-400 rounded-[25px] max-w-[80%] mx-4 text-gray-700 font-medium my-2 shadow">
        {{ text }} 
      </div>
    </div>
</template>
<script setup>
  defineProps({
    text: String
  })
</script>