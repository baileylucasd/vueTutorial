<template>
  <div id="app">
    <h1>"VueJS Experiment by {{ me }}"</h1>
    <h2>Personal Info
      Name: {{myInfo.name}}<br/>
      Semester: {{myInfo.semester}} {{myInfo.year}}<br/>
      Courses I am taking
      <ol>
        <li v-for="(c,pos) in myInfo.courses" :key="pos">{{c.name}}
          ({{c.credits}} credits)</li>
      </ol>
    </h2>
    <table>
      <tr><td>Course</td><td>Credits</td></tr>
      <tr v-for="(c,pos) in myInfo.courses" :key="pos">
        <td>{{c.name}}</td>
        <td>{{c.credits}}</td>
      </tr>
    </table>
    <CourseCard v-for="(c,pos) in myInfo.courses" :key="pos"
  v-bind:name="c.name" v-bind:num-credits="c.credits"></CourseCard>
    <img alt="Vue logo" src="./assets/logo.png">
    <!--HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/-->
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import HelloWorld from './components/HelloWorld.vue';
import CourseCard from "./components/CourseCard.vue";

@Component({
  components: {
    HelloWorld, CourseCard
  },
})

export default class App extends Vue {
  readonly me = "Lucas Bailey";
  readonly myInfo = {
    name: "Lucas Bailey",
    semester: "Winter",
    year: 2021,
    courses: [
      { name: "CIS380 Game Design", credits: 3},
      { name: "CIS371 Web Application Development", credits: 3},
    ],
  };
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
