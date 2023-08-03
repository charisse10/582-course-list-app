<template>
  <!-- <button @click="innerAdd">Add</button> -->
  <!-- <button @click="outerAdd">Add to Parent</button> -->
  <div class="card">
    <div>Course Name: {{ courses[0].name }}</div>
    <div>Description: {{ courses[0].description }}</div>
    <div>ID: {{ courses[0].id }}</div>
    <div>Credit: {{ courses[0].credits }}</div>
    <div>Teacher: {{ courses[0].teacher }}</div>
    <div>Time: {{ courses[0].time }}</div>
    <!-- <button @click="AddingCourse">Add</button> -->
    <button @click="toggleAddingCourse">
      {{ isAdded ? "Remove" : "Add" }}
    </button>
  </div>
</template>

<script>
export default {
  name: "CourseItem",
  props: {
    updateCount: Function,
  },
  data() {
    return {
      isAdded: false,
      courses: [
        {
          name: "Web Framework",
          description: "Learn how to build web apps",
          id: "582-41B",
          credits: 3,
          teacher: "Peter",
          time: "14:00-17:30",
        },
        {
          name: "Mobile App",
          description: "Learn how to build mobile apps",
          id: "582-41C",
          credits: 3,
          teacher: "John",
          time: "14:00-17:30",
        },
        {
          name: "Data Science",
          description: "Learn how to analyze data",
          id: "582-41D",
          credits: 3,
          teacher: "Mary",
          time: "14:00-17:30",
        },
      ],
    };
  },
  methods: {
    // AddingCourse() {
    //   // this.$emit("outerAdd");
    // },
    toggleAddingCourse() {
      this.isAdded = !this.isAdded;
      this.updateCount(this.isAdded);
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
