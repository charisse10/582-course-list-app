<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <CourseItem @add-course="addCourse" />
  <h4>Number of Courses: {{ count }}</h4>
  <!-- <CourseItem v-for="student in students" :key="student.id" /> -->
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import CourseItem from "./components/CourseItem.vue";

export default {
  name: "App",
  data() {
    return {
      count: 0,
    };
  },
  components: {
    // HelloWorld,
    CourseItem,
  },
  methods: {
    addCourse() {
      this.count++;
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
