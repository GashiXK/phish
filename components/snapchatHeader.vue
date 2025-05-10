<template>
  <header class="flex items-center justify-between w-full p-4 bg-[#FFFC00] shadow-md sticky top-0 z-50">
    <div class="flex items-center space-x-2">
      <!-- Snapchat Ghost Logo -->
      <!-- <div class="h-8 w-8 flex items-center justify-center">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          width="28"
          height="28"
          fill="#000000"
        >
          <path d="M12 2c5.523 0 10 4.477 10 10s-4.477 10-10 10S2 17.523 2 12 6.477 2 12 2zm0 2a8 8 0 1 0 0 16 8 8 0 0 0 0-16zm0 6a2 2 0 0 1 2 2v1h1a2 2 0 0 1 0 4h-1v1a2 2 0 0 1-4 0v-1H9a2 2 0 0 1 0-4h1v-1a2 2 0 0 1 2-2z"/>
        </svg>
      </div> -->
      
      <!-- Snapchat Text Logo -->
      <span class="font-bold text-black text-xl tracking-tighter">Snapchat</span>
    </div>
    
    <!-- Profile Icon -->
    <button class="p-1 rounded-full hover:bg-black/10 transition-colors">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        viewBox="0 0 24 24"
        fill="none"
        stroke="currentColor"
        stroke-width="2"
        stroke-linecap="round"
        stroke-linejoin="round"
        class="text-black"
      >
        <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"/>
        <circle cx="12" cy="7" r="4"/>
      </svg>
    </button>
  </header>
</template>

<script setup>
// No reactive state needed for this component
</script>

<style scoped>
/* Custom Snapchat yellow color */
header {
  background-color: #FFFC00;
}

/* Better logo alignment */
svg {
  display: block;
  margin: auto;
}
</style>