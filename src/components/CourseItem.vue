<template>
  <h2>List of Courses</h2>
  <h4>Number of Courses: {{ count }}</h4>
  <!-- <button @click="innerAdd">Add</button> -->
  <!-- <button @click="outerAdd">Add to Parent</button> -->
  <div class="card">
    <div>Course Name: {{ courses[0].name }}</div>
    <div>Description: {{ courses[0].description }}</div>
    <div>ID: {{ courses[0].id }}</div>
    <div>Credit: {{ courses[0].credits }}</div>
    <div>Teacher: {{ courses[0].teacher }}</div>
    <div>Time: {{ courses[0].time }}</div>
    <button @click="addApp">Add Course</button>
  </div>
</template>

<script>
export default {
  name: "CourseItem",
  data() {
    return {
      count: 0,
      courses: [
        {
          name: "Web Framework",
          description: "Learn how to build web apps",
          id: "582-41B",
          credits: 3,
          teacher: "Peter",
          time: "14:00-17:30",
        },
      ],
    };
  },
  methods: {
    addCourse() {
      this.$emit("add-course");
    },
  },
};
</script>

<style>
.card {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 20px;
  text-align: left;
}
</style>
