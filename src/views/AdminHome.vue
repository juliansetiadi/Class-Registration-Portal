<template>
  <div id="adminhome">
    <div class="dashboard">
      <div v-for="action in adminActions" :key="action.title" class="action-box" @click="performAction(action.link)">
        <h2>{{ action.title }}</h2>
      </div>
      <!-- Add the logout button -->
      <button class="logout-button" @click="logout">Logout</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AdminHome',
  data() {
    return {
      adminActions: [
        { title: 'View Teaching Schedule', link: '/adminscheduleview' },
        { title: 'Course Search', link: '/search' },
      ],
    };
  },
  methods: {
    performAction(link) {
      // For Vue Router, you would use this.$router.push(link)
      // For simplicity, we're using window.location for this example
      window.location.href = link;
    },
    logout() {
      // For Vue Router, you would use this.$router.push('/login')
      // For simplicity, we're using window.location for this example
      window.location.href = '/';
    },
  },
};
</script>

<style scoped>
#adminhome {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  background-color: #0055b7;
  color: #2c3e50;
  height: 100vh;
  display: flex;
  flex-direction: column; /* Adjusted for a column layout */
  justify-content: center;
  align-items: center;
}

.admin-title {
  font-size: 24px;
  color: white;
  margin-bottom: 20px;
}

.dashboard {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  background-color: #e6f7ff;
  padding: 20px;
  justify-items: center;
  align-content: center;
  min-height: 100vh;
}

.action-box {
  border: 2px solid #99ccf3;
  text-align: center;
  cursor: pointer;
  background-color: #f0faff;
  box-shadow: 0 4px 8px 0 rgba(153, 204, 243, 0.2);
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
  width: 100%;
  max-width: 300px;
  border-radius: 10px; /* Add this line for rounded corners */
}

.action-box:hover {
  background-color: #d1e9ff;
  transform: translateY(-5px);
  box-shadow: 0 6px 12px 0 rgba(153, 204, 243, 0.3);
}

.logout-button {
  padding: 10px;
  border: none;
  border-radius: 5px; /* Add this line for rounded buttons */
  cursor: pointer;
  font-size: 18px;
  background-color: #ff6347; /* Adjust color as needed */
  color: white;
  margin-top: 20px;
}

.logout-button:hover {
  background-color: #cc4c3b; /* Adjust color as needed */
}
</style>
