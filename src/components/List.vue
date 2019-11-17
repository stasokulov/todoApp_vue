<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <ul>
      <Item
        :todo="todo"
        :key="todo.id"
        @remove-todo="deleteItem"
        v-for="todo in todos"
      />
    </ul>
  </div>
</template>

<script>
import Item from '@/components/Item.vue'

export default {
  name: 'List',
  props: {
    msg: String,
    todos: Array,
  },
  methods: {
    deleteItem(id) {
      this.$emit('delete-item', id)
    }
  },
  components: {
    Item
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  display: flex;
  flex-direction: column;
  align-items: center;
  list-style-type: none;
  padding: 0;
}
li {
  display: flex;
  justify-content: space-between;
  margin: 10px;
  width: 300px;
}
</style>
