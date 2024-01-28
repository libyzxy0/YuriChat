<script setup>
  const isMenuOpen = ref(false);
  const messages = ref([]);
  messages.value.push({ type: "system", text: "Hello, I'm Yuri, how can i assist you today?" })
  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
  }
  const onMessage = async (message) => {
  try {
    messages.value.push({ type: "user", text: message, timestamp: Date.now() })

    const response = await fetch(`http://localhost:5000/process?message=${message}`);
    const { text } = await response.json();
    messages.value.push({ type: "system", text: text, timestamp: Date.now() })
  } catch (err) {
    console.error(err);
  }
}
</script>

<template>
  <main class="h-screen w-full">
     <Sidebar :isActive="isMenuOpen ? 'ok' : ''" /> 
    <Navbar @handleMenuClick="toggleMenu" :isActive="isMenuOpen ? 'ok' : ''" />
    <div class="flex justify-end">
      <MessagesContainer :messages="messages" />
      <InputContainer @onMessage="onMessage" />
    </div>
  </main>
</template>
