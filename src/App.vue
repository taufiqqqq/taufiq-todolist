<template>
  <div class="container" style="margin-top: 20px;">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">Todo-List Taufiq</h5>
        <div class="row">
          <div class="col-10">
            <input v-model="todo" type="text" class="form-control" @keyup.enter="add"/>
          </div>
          <div class="col-2">
            <button class="btn btn-success" @click="add">ADD</button>
          </div>
        </div>
        <list :todos="todos" @deleteTodo="deleteTodo" />
      </div>
    </div>
  </div>
</template>

<script>
import List from "./components/List.vue";

export default {
  components: { List },
  data() {
    return {
      todo: "",
      todos: []
    }
  },
  methods: {
    add() {
      this.todos.unshift(this.todo);
      this.too = "";
    },
    deleteTodo(todoIndex) {
      this.todos = this.todos.filter((item, index) => {
        if (index != todoIndex) {
          return item
        }
      })
    }
  }
}
</script>