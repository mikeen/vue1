<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <todo-list v-bind:todos="todos"></todo-list>
  </div>
</template>

<script>
// @ is an alias to /src
import TodoList from '../components/TodoList'

export default {
  name: 'home',
  components: {
    TodoList
  },
  data() {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
}
</script>
