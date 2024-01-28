<template>
  <div class="fixed bottom-0 h-auto flex flex-col w-full md:w-[70%] bg-slate-800 opacity-90 pt-3 md:pt-5 shadow-md border-t border-gray-700 z-10">
    <div class="flex flex-row justify-around items-center w-full">
    <textarea v-model="message" class="bg-slate-700 resize-none px-4 h-[3rem] md:h-[3.5rem] py-3 md:px-6 md:py-4 md:text-md rounded-full outline-none border-none ml-3 shadow w-[80%] text-gray-100 font-medium ring-1 ring-gray-600 focus:ring-purple-400" placeholder="Enter your question."></textarea>
    <button @click="sendMessage" class="flex justify-center items-center w-20 mx-3 text-white bg-green-400 rounded-full py-3 md:py-4 shadow-md hover:bg-purple-400 transition-all duration-300 ring-1 ring-green-300">
      <IconsPaperPlane />
    </button>
    </div>
    <p class="text-gray-400 text-center mx-5 mt-4 text-sm md:text-lg pb-3"><b class="text-green-400">YuriAI</b> is currently under development, so you might encounter some inaccuracies in responses. If there's an issues please go to <a class="text-green-300 hover:underline" href="https://yuri.deno.dev">https://yuri.deno.dev/help</a></p>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        message: ""
      }
    }, 
    methods: {
      sendMessage() {
        this.$emit('onMessage', this.message);
        this.message = "";
      }
    }
  }
</script>