<template>
    <div>
      <p>Loading...</p>
    </div>
  </template>
  
  <script setup>
  import { onMounted } from 'vue';
  import { useAuth0 } from '@auth0/auth0-vue';
  
  const { handleRedirectCallback } = useAuth0();
  
  onMounted(async () => {
    await handleRedirectCallback();
    // Redirect the user after login
    this.$router.push('/home'); // or wherever you want to redirect
  });
  </script>
  