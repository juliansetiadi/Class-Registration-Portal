<template>
    <div class="dashboard">
      <div v-for="service in services" :key="service.title" class="service-box" @click="goToService(service.link)">
        <h2>{{ service.title }}</h2>
      </div>
      <button class="logout-button" @click="logout">Logout</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Dashboard',
    data() {
      return {
        services: [
          { title: 'Class Enrollment/Drop', link: '/class' },
          { title: 'Course Search',  link: '/search' },
          { title: 'Student: Home',  link: '/homepage' },
          { title: 'View Schedule', link: '/schedule' },
          { title: 'Registration Portal', link: '/registration' },
        ]
      };
    },
    methods: {
      goToService(link) {
        // For Vue Router, you would use this.$router.push(link)
        // For simplicity, we're using window.location for this example
        window.location.href = link;
      },
      logout() {
        window.location.href = '/';
      }
    }
  };
  </script>
  
  <style>
.dashboard {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  background-color: #e6f7ff; /* Light blue background for the whole dashboard */
  padding: 20px; /* Padding around the grid */
  justify-items: center; /* Centers the boxes horizontally */
  align-content: center; /* Centers the boxes vertically */
  min-height: 100vh; /* Ensures the dashboard takes up the minimum height of the viewport */
}

.service-box {
  border: 2px solid #99ccf3; /* Light blue border */
  padding: 10px;
  text-align: center;
  cursor: pointer;
  background-color: #f0faff; /* Very light blue for box background */
  box-shadow: 0 4px 8px 0 rgba(153, 204, 243, 0.2); /* Soft shadow with light blue tint */
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out; /* Smooth transitions for hover effects */
  width: 100%; /* Set a width to the boxes */
  max-width: 300px; /* Maximum width for the boxes to not stretch too wide */
}

.service-box:hover {
  background-color: #d1e9ff; /* Slightly darker light blue on hover */
  transform: translateY(-5px); /* Slight raise effect on hover */
  box-shadow: 0 6px 12px 0 rgba(153, 204, 243, 0.3); /* Increased shadow on hover for depth */
}

.service-box img {
  max-width: 100px;
  margin-bottom: 10px;
}

.service-box h2 {
  margin: 10px 0;
  color: #0055b7; /* Darker blue for text */
}

.service-box p {
  color: #666;
}
.logout-button {
  padding: 10px;
  border: none;
  border-radius: 5px;
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
