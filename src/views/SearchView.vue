<template>
  <div id="course-search">
    <h1 class="page-title">Course Search</h1>
    <button class="home-button go-back" @click="goBack">Go Back</button>
    <div class="department-container">
      <div v-for="(department, departmentIndex) in uniqueDepartments" :key="departmentIndex" class="department">
        <h2 class="department-title">{{ department }}</h2>
        <div class="class-list">
          <div v-for="course in getCoursesByDepartment(department).sort((a, b) => a.course_number.N - b.course_number.N)" :key="course.course_number.N" class="course">
            <p class="course-info">
              <span class="course-number">{{ department }} {{ course.course_number.N }}</span>
              <br />
              <span class="course-name">{{ course.course_name.S }}</span>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      courses: [],
    };
  },
  async mounted() {
    // Only fetch data if courses are not already populated
    if (this.courses.length === 0) {
      try {
        const response = await fetch('https://jyiq3dyf2h.execute-api.us-east-1.amazonaws.com/prod/classes');
        const data = await response.json();
        console.log('Data from API:', data);

        if (data.statusCode === 200) {
          this.courses = JSON.parse(data.body);
        } else {
          console.error('Error fetching data:', data);
        }
      } catch (error) {
        console.error('Error fetching data:', error);
      }
    }
  },
  computed: {
    uniqueDepartments() {
      // Get unique department names
      return [...new Set(this.courses.map((course) => course.department.S))];
    },
  },
  methods: {
    getCoursesByDepartment(departmentName) {
      // Filter courses by department
      return this.courses.filter((course) => course.department.S === departmentName);
    },
    goBack() {
      // Add code to navigate back to the previous page
      this.$router.go(-1);
    },
  },
};
</script>

<style scoped>
#course-search {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  background-color: #0055b7;
  color: white;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.page-title {
  font-size: 24px;
  margin: 20px 0;
}

.home-button {
  background-color: #0055b7;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 18px;
  margin-bottom: 20px;
}

.go-back:hover {
  background-color: #004488;
}

.department-container {
  display: flex;
  gap: 20px;
  flex-wrap: wrap;
  justify-content: center;
}

.department {
  background-color: #0055b7;
  padding: 20px;
  border-radius: 10px;
  width: 300px;
  text-align: center;
  color: white;
  margin-bottom: 20px;
}

.department-title {
  font-size: 20px;
  margin-bottom: 10px;
}

.class-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.course {
  background-color: white;
  padding: 15px;
  border-radius: 5px;
  width: 250px;
  text-align: center;
  color: #0055b7;
}

.course-info {
  margin: 0;
}

.course-number {
  font-size: 18px;
  font-weight: bold;
}

.course-name {
  font-size: 16px;
}
</style>
