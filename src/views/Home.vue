<template>
  <v-container>
    <TodoNew
      :todo="newTodo"
      :newTodo="true"
      @addtodo="todos.unshift({...newTodo});saveTodos()"
      @delalltodos="deleteAllTodos()"
    />
    <v-divider></v-divider>
    <Todo
      v-for="(todo,index) in todos"
      :todo="todo"
      :key="index"
      :index='index'
      @deltodo="deleteTodo($event)"
      @savetodos="saveTodos()"
    />
  </v-container>
</template>

<script>
export default {
  data: () => ({
    newTodo: { done: false, text: '', editable: false },
    todos: []
  }),
  components: {
    Todo: () => import('@/components/Todo.vue'),
    TodoNew: () => import('@/components/TodoNew.vue')
  },
  methods: {
    deleteTodo(event){
      this.todos = this.todos.filter((todo, index) => {
        if(index==event){
          return false
        }else return true
      })
      this.saveTodos();
    },
    saveTodos(){
      localStorage.setItem('mytodos', JSON.stringify(this.todos));
    },
    getTodos(){
      let todos = JSON.parse(localStorage.getItem('mytodos'));
      this.todos = todos?todos:[];
    },
    deleteAllTodos(){
      this.todos = [];
      this.saveTodos();
    }
  },
  created(){
    this.getTodos();
  }
}
</script>
