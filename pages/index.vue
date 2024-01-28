<script setup>
  const isMenuOpen = ref(false);
  const messages = ref([]);
  const welcomeMessages = ["Hey there! 😊 I'm Yuri, here to help you out. What can I do for you today?", "Hi! 🌟 Yuri here, ready to assist you. How can I make your day better?", "Hello! 👋 It's Yuri, your friendly AI helper. What's on your mind?", "Greetings! 🌼 Yuri at your service! What can I do to brighten your day?"];
  messages.value.push({ type: "system", text: welcomeMessages[Math.floor(Math.random() * welcomeMessages.length)] })
  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
  }
  const onMessage = async (message) => {
  try {
    messages.value.push({ type: "user", text: message, timestamp: Date.now() })

    const response = await fetch(`https://yuriai.deno.dev/process?message=${message}`);
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
