<template>
  <div id="app">
    <div class="container">
      <h1> VUE TODO! </h1>
        <input class="input" v-model="newToDo "type="text" name="" id="">
        <button v-on:click="add()" class="add-button"> Add </button>
        <ul style="list-style-type:none"> 
          <li v-for="(todo, i) in existingToDo">
            <span> {{ i + 1 }} : {{ todo.text}} </span>
            <button class="delete-button" v-on:click="delete()"> X </button>
          </li>
        </ul>
      
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      newToDo: "",
      existingToDo: [
        { text: "Deliberate Practice work", id: 0 },
        { text: "Apply to Jobs!", id: 1 },
        { text: "CS50 Lecture 2", id: 2 },
      ],
    };
  },
  methods: {
    add() {
      this.existingToDo.push({ text: this.newToDo, id: new Date().valueOf() });
      this.newToDo = "";
    },
    delete() {
      this.existingToDo.splice(i);
    },
  },
};
</script>




<style>
</style>
