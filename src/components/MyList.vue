<template>
  <ul class="todo-main">
    <item v-for="todo in todoList" :key="todo.id" 
    :todo="todo"></item>
  </ul>
</template>

<script>
import Item from './MyItem.vue'
export default {
  components: { Item },
  name: 'MyList',
  props: ['todoList']
}
</script>

<style scoped>
/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}
.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}
</style>