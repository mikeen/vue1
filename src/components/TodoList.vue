<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    
    <todo-item class='ui centered card' v-for="todo in todos" v-bind:todo="todo">
    </todo-item>
  </div>
</template>

<script>
import TodoItem from './TodoItem';

export default {
    components: {TodoItem},
    props: {
        todos: Array
    }
}
</script>



<style scoped>

</style>
