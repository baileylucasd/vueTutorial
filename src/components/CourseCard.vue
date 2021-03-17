<template>
  <div id="crs">
    <h3>Course: {{name}}</h3>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class CourseCard extends Vue {
  @Prop() readonly numCredits!: number;
  @Prop() readonly name!: string;
}
</script>

<style>
#crs {
  display: inline-block;
  border: 2px solid hsl(30, 90%, 50%);
  border-radius: 0.5em;
  padding: 1em;
  margin: 0.6em;
  box-shadow: 3px 5px 6px 7px hsla(30, 55%, 50%, 0.4);
}
</style>