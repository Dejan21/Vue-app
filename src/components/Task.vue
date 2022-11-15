<template>
  <div class="container">
    <h1>My favorite colors</h1>
    <input
      class="input" 
      type="text" 
      placeholder="Color name" 
      v-model="newColor" />
    <button class="btn" @click="addColor">Add color</button>
    <p>Color collection</p>
    <div class="form">
      <ul v-for="task in tasks" :key="task.id">
        <li>{{ task.colors }}</li>
        <div class="button">
          <button @click="$emit('remove')">Remove Color</button>
        </div>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "TaskComponent",
  props: ["tasks"],
  components: {},
  data() {
    return {
      newColor: "",
    };
  },
  methods: {
    addColor() {
      if (this.newColor) {
        // eslint-disable-next-line vue/no-mutating-props
        this.tasks.push({
          colors: this.newColor,
        });
        this.newColor = "";
      }
    },
  },
};
</script>


<style scoped>
.form{
   width: 300px;
   margin: auto;
   display: grid;
}

h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  
}
.input{
  width: 200px;
  height: 30px;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.button{
  width: 140px;
  height: 20px;
  float: right;
  display: flex;
  justify-content: end;
}
.btn{
  height: 36px;
  color: white;
  background-color: black;
}
</style>
