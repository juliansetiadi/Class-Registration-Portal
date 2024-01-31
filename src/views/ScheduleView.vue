<template>
    <div class="schedule-viewer">
      <h1>Schedule Viewer</h1>
      
      <!-- Date Selector -->
      <div class="date-selector">
        <label for="selectedDate">Select a Date: </label>
        <input type="date" id="selectedDate" v-model="selectedDate" @change="loadSchedule" />
      </div>
      
      <!-- Schedule Display -->
      <div class="schedule">
        <table>
          <thead>
            <tr>
              <th>Time</th>
              <th>Class</th>
              <th>Location</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="event in schedule" :key="event.id">
              <td>{{ event.time }}</td>
              <td>{{ event.name }}</td>
              <td>{{ event.location }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedDate: '', // Store the selected date
        schedule: [],      // Store the schedule data
      };
    },
    methods: {
      loadSchedule() {
        // Fetch the schedule data for the selected date and update this.schedule
        // You can make an API call or load data from your data source here
      },
    },
    created() {
      // Initialize the schedule when the component is created, you can load data for today's date or a default date
      this.selectedDate = new Date().toISOString().slice(0, 10); // Default to today's date
      this.loadSchedule();
    },
  };
  </script>
  
  <style scoped>
  .schedule-builder {
    text-align: center;
  }
  
  .date-selector {
    margin-bottom: 20px;
  }
  
  .schedule table {
    width: 100%;
    border-collapse: collapse;
  }
  
  .schedule th, .schedule td {
    border: 1px solid #ccc;
    padding: 8px;
    text-align: center;
  }
  
  .schedule th {
    background-color: #f2f2f2;
  }
  
  .schedule tr:nth-child(even) {
    background-color: #f2f2f2;
  }
  </style>
  