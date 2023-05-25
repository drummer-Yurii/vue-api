<script setup>
import { ref } from 'vue';
import { useAuthStore } from '../stores/auth';

const authStore = useAuthStore();

const email = ref('');
</script>

<template>
    <form class="mx-auto max-w-md" @submit.prevent="authStore.handleForgotPassword(email)">
      <h3 class="font-bold">Forgot password</h3>

      <div class="my-6">
        <label for="email" class="mb-2 block text-sm font-medium text-gray-900 dark:text-gray-300">Your email</label>
        <input 
            type="email" 
            id="email" 
            v-model="email" 
            class="block w-full rounded-lg border border-gray-300 bg-gray-50 p-2.5 text-sm text-gray-900 focus:border-blue-500 focus:ring-blue-500 dark:border-gray-600 dark:bg-gray-700" 
            placeholder="email@laraveller.com">
      </div>
      <button class="w-full rounded-lg bg-blue-700 px-5 py-2.5 text-center text-sm font-medium text-white max-w-[100px]">Submit</button>
    </form>
</template>