<template>
    <div class="registration-view">
      <h1>Class Registration Portal</h1>
      <form @submit.prevent="register">
        <div class="form-group">
          <label for="name">Name:</label>
          <input v-model="user.name" type="text" id="name" required />
        </div>
        <div class="form-group">
          <label for="email">Email:</label>
          <input v-model="user.email" type="email" id="email" required />
        </div>
        <div class="form-group">
          <label for="password">Password:</label>
          <input v-model="user.password" type="password" id="password" required />
        </div>
        <div class="form-group">
          <label for="className">Class Name:</label>
          <input v-model="user.className" type="className" id="className" required />
        </div>
        <div class="form-group">
          <label for="permissionNumber">Permission Number:</label>
          <input v-model="user.permissionNumber" type="permissionNumber" id="permissionNumber" required />
        </div>
        <button type="submit">Register</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        user: {
          name: '',
          email: '',
          password: '',
          className: '',
          permissionNumber: '',
        }
      };
    },
    methods: {
      register() {
        console.log('User Registration', this.user);
        // Here you would typically send the user data to a server
        // For this example, we just log it to the console
        alert('Registration Successful!');
      }
    }
  };
  </script>
  
  <style scoped>
  .registration-view {
    max-width: 400px;
    margin: 40px auto;
    padding: 20px;
    text-align: center;
  }
  
  .form-group {
    margin-bottom: 20px;
  }
  
  label {
    display: block;
    margin-bottom: 10px;
  }
  
  input {
    width: 100%;
    padding: 8px;
    box-sizing: border-box;
  }
  
  button {
    padding: 10px 15px;
    font-size: 16px;
  }
  </style>
  