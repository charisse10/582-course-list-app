<template>
  <!-- <button @click="innerAdd">Add</button> -->
  <!-- <button @click="outerAdd">Add to Parent</button> -->
  <div class="card-flex">
    <div v-for="course in courses" :key="course.id" class="card">
      <div class="name">{{ course.name }}</div>
      <div>{{ course.description }}</div>
      <div>ID: {{ course.id }}</div>
      <div>Credit: {{ course.credits }}</div>
      <div>Hours: {{ course.hours }}</div>
      <div>Instructor: {{ course.instructor }}</div>
      <div>
        Number of students:{{
          course.clicks === 20 ? "FULL" : course.clicks + " of 20"
        }}
      </div>
      <!-- <button @click="AddingCourse">Add</button> -->
      <button
        @click="toggleAddingCourse(course)"
        :disabled="course.clicks >= 20"
      >
        {{ course.isAdded ? "Remove" : "Add" }}
      </button>
    </div>
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
      courses: [
        {
          name: "Web Framework",
          description: "Learn how to build web apps",
          id: "582-41B",
          credits: 3,
          hours: 60,
          instructor: "Peter",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Mobile App",
          description: "Learn how to build mobile apps",
          id: "582-41C",
          credits: 3,
          hours: 90,
          instructor: "John",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Data Science",
          description: "Learn how to analyze data",
          id: "582-41D",
          credits: 3,
          hours: 70,
          instructor: "Mary",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Machine Learning",
          description: "Learn how to build machine learning models",
          id: "582-41E",
          credits: 3,
          hours: 80,
          instructor: "Tom",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Deep Learning",
          description: "Learn how to build deep learning models",
          id: "582-41F",
          credits: 3,
          hours: 120,
          instructor: "Jerry",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Computer Vision",
          description: "Learn how to build computer vision models",
          id: "582-41G",
          credits: 3,
          hours: 100,
          instructor: "Peter",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Natural Language Processing",
          description: "Learn how to build NLP models",
          id: "582-41H",
          credits: 3,
          hours: 50,
          instructor: "John",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Data Visualization",
          description: "Learn how to visualize data",
          id: "582-41I",
          credits: 3,
          hours: 90,
          instructor: "Mary",
          isAdded: false,
          clicks: 0,
        },
        {
          name: "Data Mining",
          description: "Learn how to mine data",
          id: "582-41J",
          credits: 3,
          hours: 40,
          instructor: "Tom",
          isAdded: false,
          clicks: 0,
        },
      ],
    };
  },
  methods: {
    // AddingCourse() {
    //   // this.$emit("outerAdd");
    // },
    toggleAddingCourse(course) {
      if (course.clicks < 20) {
        course.isAdded = !course.isAdded;
        this.updateCount(course.isAdded);
        course.clicks++;
      }
    },
  },
};
</script>

<style scoped lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.card-flex {
  max-width: 90%;
  margin: 25px auto 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 25px;

  .card {
    width: calc(33.33% - 25px);
    border: 2px solid #cacaca;
    border-radius: 10px;
    padding: 20px;
    text-align: center;

    .name {
      color: rgb(5, 34, 129);
      font-size: 20px;
      font-weight: bold;
      text-align: center;
    }

    button {
      margin-top: 10px;
      padding: 5px 30px;
      border-radius: 25px;
      border: none;
      background-color: #088318;
      color: #fff;
      font-size: 18px;
      font-weight: bolder;

      cursor: pointer;
    }

    button:hover {
      background-color: #036d11;
    }
  }
}
</style>
