with admin button:

<template>
  <div id="app">
    <div class="login-container">
      <div class="logo">
        <h1><img src="@/assets/CustomLoginLogo.png" alt="UCONN Logo"></h1>
      </div>
      <div class="login-form">
        <button class="login-button" @click="handleLogin('student')">Student Login</button>
        <button class="admin-login-button" @click="handleLogin('admin')">Admin Login</button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { useAuth0 } from "@auth0/auth0-vue";

const { loginWithRedirect } = useAuth0();

const handleLogin = (role) => {
  const targetRoute = role === 'admin' ? '/adminhome' : '/dashboard';

  loginWithRedirect({
    appState: {
      target: targetRoute,
    },
  });
};
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  background-color: #0055b7;
  color: #2c3e50;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.login-container {
  background-color: white;
  padding: 50px;
  border-radius: 10px;
  width: 300px;
  text-align: center;
}

.logo h1 {
  margin: 0;
  font-size: 50px;
  color: #0055b7;
  font-weight: bold;
}

.login-form {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

input {
  padding: 15px;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 16px;
}

button {
  padding: 15px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

.login-button {
  background-color: #0055b7;
  color: white;
}

.admin-login-button {
  background-color: #f1f1f1;
  color: #333;
}
</style>
