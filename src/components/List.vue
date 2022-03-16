<template>
  <div style="margin-top: 20px;">
    <ul class="list-group">
      <li v-for="(todo, index) in todos" :key="index" class="list-group-item">
        <div class="row">
          <div class="col">
            <span>{{ todo }}</span>
          </div>
          <div class="col-auto">
            <div class="row gx-2">
              <div class="col">
                <button @click="deleteTODO(index)" class="btn btn-danger">X</button>
              </div>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    todos: {
      type: Array,
      default: []
    }
  },
  methods: {
    deleteTODO(index) {
      this.$emit('deleteTodo', index)
    }
  }
}
</script>