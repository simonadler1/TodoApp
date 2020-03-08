<template>
  <div>
    <h1>To Do List</h1>

    <div v-for="todo in this.todolist" :key="todo.title">
      <div>
        <div>
          {{ todo.title }}
        </div>
        <div>
          <button @click="deletetodo(todo)">
            <i class="fas fa-trash-alt"></i>
          </button>
        </div>
      </div>
    </div>
    <input type="text" v-model="addtodo" />
    <button @click="addTodo(addtodo)">Add Todo</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
  data() {
    return {
      addtodo: "",
      todolist: [{ title: "todo 1" }, { title: "todo 2" }]
    };
  },
  methods: {
    addTodo(newtodo) {
      let newtodoitem = { title: `${newtodo}` };
      this.todolist.push(newtodoitem);
      this.addtodo = "";
    },
    deletetodo(todo) {
      this.todolist.splice(this.todolist.indexOf(todo), 1);
    }
  }
};
</script>
