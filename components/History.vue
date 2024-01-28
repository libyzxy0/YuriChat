<template>
  <li class="text-gray-300 py-2 px-2 transition-all duration-300 hover:bg-gray-600 flex flex-row border-b border-gray-600 md:py-4">
        <button class="mr-2">
        <IconsGoTo />
        </button>
        <p class="md:text-xl">{{ text }}</p>
        </li>
</template>
<script setup>
  defineProps({
    text: String
  })
</script>