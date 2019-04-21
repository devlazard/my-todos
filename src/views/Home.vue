<template>
  <v-container>
    <v-progress-linear
      v-model="progress"
      :value="progress"
      color="green"
      style="margin-top: 0px;"
      />
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
  computed: {
    progress(){
      if(this.todos.length==0)
        return 100;
      else {
        let value = 0;
        this.todos.map(({done}) => {
          if(done) value += 100/this.todos.length;
        })
        return value;
      }
    }
  },
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
    updateProgress(){

    },
    saveTodos(){
      localStorage.setItem('mytodos', JSON.stringify(this.todos));
    },
    getTodos(){
      let todos = JSON.parse(localStorage.getItem('mytodos'));
      this.todos = todos?todos:[];
    },
    deleteAllTodos(){
      this.todos = this.todos.filter(todo => {
        if(todo.done) return false
        else return true
      });
      this.saveTodos();
    }
  },
  created(){
    this.getTodos();
  }
}
</script>
