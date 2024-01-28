<template>
  <div class="flex flex-col pt-20 h-screen w-full md:w-[70%] md:text-xl">
    <template v-for="message in sortedMessages" :key="message.id">
      <MessageMe v-if="message.type === 'user'" :text="message.text" />
      <MessageYuri v-else :text="message.text" />
    </template>
  </div>
</template>

<script setup>
  import { defineProps, computed } from 'vue';

  const props = defineProps({
    messages: Array
  });

  const sortedMessages = computed(() => {
    return props.messages.slice().sort((a, b) => a.timestamp - b.timestamp);
  });
</script>