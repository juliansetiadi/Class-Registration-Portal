<template>
    <div id="home">
      <h1 class="page-title">Student Administration Portal</h1>
      <div class="button-container">
        <button class="home-button view-schedule" @click="viewSchedule">View Schedule</button>
        <button class="home-button enroll-courses" @click="enrollCourses">Enroll in Courses</button>
        <button class="home-button course-search" @click="courseSearch">Course Search</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'HomePage',
    methods: {
      viewSchedule() {
        //code to go to page
      },
      enrollCourses() {
        //code to go to page
      },
      courseSearch() {
        //code to go to page
      },
    },
  };
  </script>
  
  <style scoped>
  #home {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    background-color: #0055b7;
    color: #2c3e50;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  .page-title {
    font-size: 24px;
    color: white;
    margin: 20px 0;
  }
  
  .button-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }
  
  .home-button {
    background-color: #0055b7;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 18px;
  }
  
  .view-schedule:hover, .enroll-courses:hover, .course-search:hover {
    background-color: #004488;
  }
  </style>
  