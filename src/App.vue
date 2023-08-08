<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <h1>TESTING MAC</h1>
  <h2>List of Courses</h2>
  <h4>Selected Courses: {{ count }}</h4>
  <!-- <CourseItem @outerAdd="AddCourse" /> -->
  <CourseItem :updateCount="updateCount" />

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
    updateCount(isAdded) {
      if (isAdded) {
        this.count++;
      } else {
        this.count--;
      }
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
