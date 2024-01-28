<template>
  <div class="flex justify-end">
    <div class="py-3 px-4 bg-green-400 rounded-[25px] max-w-[80%] mx-4 text-gray-700 font-medium my-2 shadow" 
         v-if="isRendered"
         :class="{ 'animate-chat-bubble': isRendered }">
      {{ text }} 
    </div>
  </div>
</template>

<script setup>
  import { ref, onMounted } from 'vue';
  
  const isRendered = ref(false);
  
  onMounted(() => {
    isRendered.value = true;
  });

  defineProps({
    text: String
  })
</script>

<style scoped>
  .animate-chat-bubble {
    animation: slideIn 0.5s ease;
  }

  @keyframes slideIn {
    from {
      transform: translateY(20px);
      opacity: 0;
    }
    to {
      transform: translateY(0);
      opacity: 1;
    }
  }
</style>
