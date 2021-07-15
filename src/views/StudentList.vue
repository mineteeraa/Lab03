<template>
  <h1>Student</h1>
  <div class="events">
    <Student v-for="student in students" :key="student.id" :student="student" />
  </div>
</template>

<script>
// @ is an alias to /src
import Student from '@/components/Student.vue'
import StudentService from '@/services/StudentService.js'

export default {
  name: 'Students',
  components: {
    Student //register it as a child component
  },
  data() {
    return {
      students: null
    }
  },
  created() {
    StudentService.getEvents()
      .then((response) => {
        this.students = response.data
      })
      .catch((error) => {
        console.log(error)
      })
  }
}
</script>
<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
