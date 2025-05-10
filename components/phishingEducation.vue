<template>
  <div class="space-y-6 max-w-2xl mx-auto">
    <div class="border-red-500 bg-red-50 dark:bg-red-900/20 text-red-600 dark:text-red-400 border rounded-lg p-4">
      <h3 class="text-xl font-bold mb-2">
        This was a phishing simulation!
      </h3>
      <p class="text-sm">
        In a real scenario, your password would have just been stolen. This was created as an educational tool.
      </p>
    </div>
    
    <div class="bg-white dark:bg-gray-800 p-6 rounded-lg shadow-md space-y-4">
      <h2 class="text-xl font-bold">Red Flags You Should Have Noticed:</h2>
      <ul class="list-disc pl-6 space-y-2">
        <li>Suspicious URL - Always check that you're on the official Snapchat domain</li>
        <li>Urgent security messages creating panic</li>
        <li>Poor grammar or unusual wording in the messages</li>
        <li>Requesting sensitive information like your current password</li>
        <li>Generic greeting instead of your actual name</li>
      </ul>
      
      <h2 class="text-xl font-bold mt-6">How to Protect Yourself:</h2>
      <ul class="list-disc pl-6 space-y-2">
        <li>Always navigate directly to websites by typing the URL</li>
        <li>Enable two-factor authentication on all accounts</li>
        <li>Don't click on links from unexpected emails or messages</li>
        <li>Check for HTTPS and the lock icon in your browser</li>
        <li>When in doubt, contact the company directly through official channels</li>
      </ul>
      
      <div class="mt-6 text-center">
        <button
          @click="window.location.reload()"
          class="inline-flex items-center justify-center rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 border border-input bg-background hover:bg-accent hover:text-accent-foreground h-10 px-4 py-2 mr-4"
        >
          Try Again
        </button>
        <button
          @click="window.open('https://www.snapchat.com/safety', '_blank')"
          class="inline-flex items-center justify-center rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 h-10 px-4 py-2 bg-[#FFFC00] hover:bg-[#E6E300] text-black"
        >
          Learn More About Online Safety
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
// No need for additional script logic since we're using basic click handlers
</script>

<style scoped>
.space-y-6 > * + * {
  margin-top: 1.5rem;
}
.space-y-4 > * + * {
  margin-top: 1rem;
}
.space-y-2 > * + * {
  margin-top: 0.5rem;
}
</style>