<template>
  <div class="flex flex-col min-h-screen bg-gray-100">
    <SnapchatHeader />
    
    <div class="container mx-auto px-4 py-8 flex-1">
      <div v-if="!isPhished" class="max-w-md mx-auto bg-white p-6 rounded-lg shadow-md space-y-6">
        <div class="space-y-4">
          <div class="flex items-center justify-center mb-4">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="32"
              height="32"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
              class="text-red-500"
            >
              <path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"></path>
              <line x1="12" y1="9" x2="12" y2="13"></line>
              <line x1="12" y1="17" x2="12.01" y2="17"></line>
            </svg>
          </div>
          
          <h1 class="text-xl font-bold text-center">Security Alert</h1>
          
          <div class="bg-red-50 border border-red-200 p-4 rounded-md text-red-800">
            <p class="font-medium">Unusual activity has been detected on your Snapchat account.</p>
          </div>
          
          <p>For your protection, we've temporarily locked your account. To restore access, please verify your identity by resetting your password.</p>
          
          <p class="text-sm text-gray-500">Reference ID: SC-78941223</p>
        </div>
        
        <PasswordForm @submit="handleFormSubmit" />
      </div>
      
      <PhishingEducation v-else />
    </div>
    
    <footer class="bg-gray-100 py-4 border-t border-gray-200">
      <div class="container mx-auto px-4 text-center text-sm text-gray-500">
        <p>© {{ new Date().getFullYear() }} | This is an educational phishing simulation</p>
      </div>
    </footer>
  </div>
</template>

<script setup>

const isPhished = ref(false);

const handleFormSubmit = () => {
  isPhished.value = true;
};
</script>

<style scoped>
/* Add any specific styles here if needed */
.min-h-screen {
  min-height: 100vh;
}
.flex-1 {
  flex: 1 1 0%;
}
</style>