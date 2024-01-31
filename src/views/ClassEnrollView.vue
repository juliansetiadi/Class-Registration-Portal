<template>
  <div id="enroll-drop-page"> <!--This is the main container for this page -->
    <div class="class-container"> <!-- This is the container for the classes-->
      <h1>Enrolled Classes</h1> <!-- Heading for the enrolled classes-->
      <table class="classes-table"> <!-- This is the table for displaying class details-->
        <thead> <!-- This is the table header-->
          <tr> <!-- This is the table row-->
            <th>Status</th> <!-- This is the collumn for enrollment status-->
            <th>Class</th> <!-- Column for class ID-->
            <th>Title</th> <!-- Column for class title-->
            <th>Units</th> <!-- Column for class units-->
            <th>Grading Basis</th> <!-- Column for class grading basis-->
            <th>Days and Times</th> <!-- Column for class schedule-->
            <th>Room / Instruction Mode</th>   <!-- Column for class room and instruction mode-->
            <th>Action</th> <!-- Column for action buttons-->
          </tr>
        </thead>
        <tbody> <!-- This is the table body-->
          <tr v-for="cls in classes" :key="cls.id"> <!-- This is the table row for each class, looping through the classes array-->
            <td>Enrolled</td> <!-- This cell shows the enrollment status-->
            <td>{{ cls.id }}</td> <!-- This cell shows the class ID-->
            <td>{{ cls.name }}</td> <!-- This cell shows the class title-->
            <td>{{ cls.units }}</td> <!-- This cell shows the class units-->
            <td>{{ cls.grading }}</td> <!-- This cell shows the class grading basis-->
            <td>{{ cls.schedule }}</td> <!-- This cell shows the class schedule-->
            <td>{{ cls.room }}</td> <!-- This cell shows the class room and instruction mode-->
            <td>
              <button class="drop-button" @click="drop(cls.id)">Drop</button>  <!-- This cell shows the drop button, which calls the drop method when clicked-->
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Enroll and Drop Page', // This is the name of the page
  data() {
    return {
      classes: [ // This is the array of classes 
        { id: 'ANTH 1000W', name: 'Peoples and Cultures of the World', units: '3.00', grading: 'Graded', schedule: 'MoWe 10-11AM, Fr 9:05-9:55AM', room: 'PBB 131 / In Person', enrolled: true }, //Each class is an object with the following properties
        { id: 'ANTH 1000W', name: 'Peoples and Cultures of the World', units: '3.00', grading: 'Graded', schedule: 'MoWe 10-11AM, Fr 9:05-9:55AM', room: 'PBB 131 / In Person', enrolled: true },
        { id: 'ANTH 1000W', name: 'Peoples and Cultures of the World', units: '3.00', grading: 'Graded', schedule: 'MoWe 10-11AM, Fr 9:05-9:55AM', room: 'PBB 131 / In Person', enrolled: true },
        { id: 'ANTH 1000W', name: 'Peoples and Cultures of the World', units: '3.00', grading: 'Graded', schedule: 'MoWe 10-11AM, Fr 9:05-9:55AM', room: 'PBB 131 / In Person', enrolled: true },
        { id: 'ANTH 1000W', name: 'Peoples and Cultures of the World', units: '3.00', grading: 'Graded', schedule: 'MoWe 10-11AM, Fr 9:05-9:55AM', room: 'PBB 131 / In Person', enrolled: true },
        { id: 'ANTH 1000W', name: 'Peoples and Cultures of the World', units: '3.00', grading: 'Graded', schedule: 'MoWe 10-11AM, Fr 9:05-9:55AM', room: 'PBB 131 / In Person', enrolled: true },
        { id: 'ANTH 1000W', name: 'Peoples and Cultures of the World', units: '3.00', grading: 'Graded', schedule: 'MoWe 10-11AM, Fr 9:05-9:55AM', room: 'PBB 131 / In Person', enrolled: true },
        // ... more class objects
      ],
    };
  },
  methods: {
    drop(classId) { // This is the drop method, which takes in the class ID as a parameter
    }, //Logic to remove the class from the classes array
  },
};
</script>

<style scoped> /* This is the container for the enrollment and drop page */
  #enroll-drop-page {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    text-align: center;
    color: #061167;
    margin-top: 60px;
  }

  .class-container {  /* This is the container for the classes */
    background-color: white;
    padding: 20px;
    border-radius: 10px;
    width: 300px;
    margin: 0 auto;
  }

  button { /*This is the style for the buttons */
    margin-left: 10px;
    padding: 10px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
  }

  .enroll-button { /*This is the style for the enroll button */
    background-color: #4caf50;
    color: white;
  }

  .drop-button {  /*This is the style for the drop button */
    background-color: #f44336;
    color: white;
  }
</style>
