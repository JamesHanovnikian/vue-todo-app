<template>
  <div id="app">
    
    <div class="container">
      <Title /> 
      <div class="card" style="width: 75%;">
        <input placeholder="Add your task" class="input" v-model="newToDo "type="text" name="" id="">
        <div>
          <button type="button" v-on:click="add()" class="btn btn-primary"> Add </button>
        </div>
        <ul class="list-group list-group-flush">
        <li class="list-group-item" v-for="(todo, i) in existingToDo">
           <span> {{ i + 1 }} : {{ todo.text}} </span>
            <button type="button" v-on:click="deleteToDo(i)" class="btn btn-danger"> <i class="fas fa-trash-alt"></i> </button>
        </li>
         </ul>
      </div>
      
    </div>
  </div>
</template>

<script>
import Title from "./components/Title.vue";

export default {
  name: "app",
  components: {
    Title,
  },
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
      if (this.newToDo === "") {
      } else {
        this.existingToDo.push({
          text: this.newToDo,
          id: new Date().valueOf(),
        });
        this.newToDo = "";
      }
    },
    deleteToDo(i) {
      this.existingToDo.splice(i, 1);
    },
  },
};
</script>




<style>
body {
  font-family: "Moon Dance", cursive;
  font-size: 4rem;
}

h1 {
  text-align: center;
}

.btn {
  font-size: 3rem;
}

.card {
  padding-top: 75px;
  background-color: #3f3c3c;
}

.card .input {
  width: 75%;
}
</style>
