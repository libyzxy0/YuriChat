<script setup>
  defineProps({
    isActive: String
  })
</script>
<template>
  <nav class="z-30 w-full h-16 flex justify-between items-center shadow fixed bg-gradient-to-tl from-slate-800 to-slate-900 bg-gradient-to-r opacity-90 filter backdrop-blur-3xl z-10">
      <h1 class="flex flex-row text-green-300 font-bold text-2xl mx-4">Yuri<b class="text-purple-400">AI</b><a class="text-gray-400 text-sm mt-2 mx-1 font-medium" href="https://libyzxy0.xyz">by libyzxy0</a></h1>
      <button @click="toggleMenu" class="mx-4 text-white hover:text-green-300 transition-all md:hidden">
        <IconsMenu v-if="isActive != 'ok'" />
        <IconsClose v-else />
      </button>
    </nav>
</template>
<script>
  export default {
    methods: {
      toggleMenu() {
        this.$emit('handleMenuClick', true)
      }
    }
  }
</script>