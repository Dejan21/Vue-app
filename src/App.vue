<template>
  <div id="app">
    <task v-bind:tasks="tasks"
          @remove="removeColor(index)"
    ></task>
  </div>
</template>



<script>
import Task from './components/Task.vue'

export default {
  name: "App",
  components: {
    Task,
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          colors: "my yellow",
        },
        {
          id: 2,
          colors: "red as i like it",
        },
        {
          id: 3,
          colors: "my grass",
        },
        {
          id: 4,
          colors: "out of the blue",
        },
        {
          id: 5,
          colors: "deep purple",
        },
        {
          id: 6,
          colors: "something",
        },
      ],
    };
  },
  methods: {
    removeColor(index){
      this.tasks.splice(index, 1)
    }
  }
};
</script>

<style>
 #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  align-items: center;
  justify-content: center;
  background-color:whitesmoke;
  width: 450px;
  height: 450px;
  margin:auto
} 
</style>
