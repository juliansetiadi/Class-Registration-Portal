<template>
    <div id="AdminScheduleView">
      <h1 class="page-title">Professor's Courses</h1>
      <table class="course-table">
        <thead>
          <tr>
            <th>Course Name</th>
            <th>Description</th>
            <th>Day/Time</th>
            <th>Room</th>
            <th>Enrollment</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(course, index) in professorCourses" :key="index" class="course-row">
            <td>{{ course.courseName }}</td>
            <td>{{ course.description }}</td>
            <td>{{ course.dayTime }}</td>
            <td>{{ course.room }}</td>
            <td>{{ course.enrollment }}</td>
          </tr>
        </tbody>
      </table>
      <button class="home-button go-back" @click="goBack">Go Back to Admin Home</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'AdminScheduleView',
    data() {
      return {
        professorCourses: [
          { courseName: 'MATH 1131', description: 'Calculus', dayTime: 'MoWeFr 9:05 - 9:55', room: 'MCHU 101', enrollment: '30/30 Enrolled' },
          { courseName: 'MATH 2210', description: 'Multivariable Calculus', dayTime: 'MoWeFr 12:20 - 1:10', room: 'ITE 121', enrollment: '28/30 Enrolled' },
          { courseName: 'MATH 3150', description: 'Analysis I', dayTime: 'TueThur 9:30 - 10:45', room: 'OAK 110', enrollment: '24/30 Enrolled' },
        ],
      };
    },
    methods: {
      goBack() {
        // Add code to navigate back to the admin home page
        this.$router.push('/adminhome'); // Replace '/adminhome' with the actual route for the admin home page
      },
    },
  };
  </script>
  
  <style scoped>
  #AdminScheduleView {
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
    color: rgb(0, 0, 0);
    margin: 20px 0;
  }
  
  .course-table {
    width: 80%;
    border-collapse: collapse;
    margin-top: 20px;
  }
  
  .course-row {
    background-color: #0055b7;
    color: white;
  }
  
  .course-row:hover {
    background-color: #004488;
  }
  
  th, td {
    padding: 10px;
    text-align: left;
    border-bottom: 1px solid #ddd;
  }
  
  th {
    background-color: #004488;
    color: white;
  }
  
  .home-button {
    background-color: #0055b7;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 18px;
    margin-top: 20px;
  }
  
  .go-back:hover {
    background-color: #004488;
  }
  </style>
  