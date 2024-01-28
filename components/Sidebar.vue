<template>
  <aside class="fixed z-20 transition-all duration-300 md:border-r md:border-gray-700 h-screen bg-slate-800 shadow border-r w-[15rem] md:w-[30%] md:left-0" :class="props.isActive == 'ok' ? ' border-gray-700 left-0' : 'border-transparent left-[-16rem]'">
    
    <ul class="mt-16 relative">
      <History text="Lorem Ipsum dolor sit amet die sind." />
      <History text="Lorem Ipsum dolor sit amet die sind." />
      <History text="Lorem Ipsum dolor sit amet die sind." />
    </ul>
    
  </aside>
</template>
<script setup>
  const props = defineProps({
    isActive: String
  })
</script>