<template>
  <div id="app">
    <div class="section">
      <div class="container">
        <div class="wrapper">
          <TodosComponent
            :todos="todosData"
            @addTodo="addTodo"
            @onDelete="deleteTodo"
          />
        </div>
      </div>

      <!-- <div class="container">
        <div class="wrapper">
          <CompletedTasksComponent :completedTasks="completedTasks" />
        </div>
      </div> -->
    </div>
  </div>
</template>

<script>
import TodosComponent from "./components/TodosComponent.vue";
// import CompletedTasksComponent from "./components/CompletedTasksComponent.vue";

export default {
  name: "App",
  components: {
    TodosComponent,
    // CompletedTasksComponent,
  },
  data() {
    return {
      todosData: [
        {
          userId: 1,
          id: 1,
          title: "Set a meeting time with Doctor",
          completed: true,
        },
        {
          userId: 1,
          id: 2,
          title: "Get bank statement for last time",
          completed: false,
        },
        {
          userId: 1,
          id: 3,
          title: "Read my Bible",
          completed: false,
        },
        {
          userId: 1,
          id: 4,
          title: "Overall checkup for weekend",
          completed: true,
        },
        {
          userId: 1,
          id: 5,
          title: "Text tailor for my Sunday dress",
          completed: false,
        },

        {
          userId: 1,
          id: 8,
          title: "Send Yimika's pictures after church",
          completed: true,
        },
        {
          userId: 1,
          id: 9,
          title: "Prepare for the new week",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo(todo) {
      this.todosData.unshift(todo);
    },
    deleteTodo(id) {
      const index = this.todosData.findIndex((todo) => todo.id === id);
      if (index !== -1) {
        this.todosData.splice(index, 1);
      }
    },

    // moveToCompleted(todo) {
    //   this.completedTasks.unshift(todo);

    //   const index = this.todosData.findIndex((t) => t.id === todo.id);
    //   if (index !== -1) {
    //     this.todosData.splice(index, 1);
    //   }
    // },

    // complete(id) {
    //   const updated_todos = this.todosData.map((todo) =>
    //     todo.id == id ? Object.assign(todo, { completed: true }) : todo
    //   );
    //   this.todosData = updated_todos;
    // },
    // deleteTodo(id) {
    //   let deleted_todos = this.todosData.filter((todo) => todo.id != id);
    //   this.todosData = deleted_todos;
    // },

    // moveToCompleted(todo) {
    //   this.completedTasks.unshift(todo);

    // const index = this.todosData.findIndex((t) => t.id === todo.id);
    // if (index !== -1) {
    //   this.todosData.splice(index, 1);
    // }
    // },
  },
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
#app {
  background-color: white;
  font-family: "Cormorant", serif;
  min-height: 100vh;
  color: white;
}

/* Media query */

@media (max-width: 768px) {
  .container {
    height: 55rem;
  }

  .todobox {
    display: flex;
    align-items: center;
    height: 50px;
  }

  .edit,
  #task,
  .remove {
    margin-right: 10px;
  }

  .todo_box {
    width: 90%;
    height: 3.5rem;

    background-color: red;
  }
  .field {
    height: 4rem;
    background-color: purple;
  }
  .new_column {
    max-width: 100%;
  }
  #task {
    width: 2rem;
    font-size: 2px;
    padding: 15px 40px;
  }

  .edit {
    font-size: 12px;
  }
  .input {
    width: 85%;
    height: 20px;
    display: flex;
    justify-content: center;
    padding: 15px;
    margin: 10px 20px;
    align-items: center;
  }
}

@media (max-width: 770px) {
  .label {
    font-size: 30px;
  }
  .input {
    font-size: 8px;
  }
  .todobox {
    display: flex;
    align-items: center;
  }
  .new_column {
    font-size: 1px;
  }
  .boxtodobox {
  }
  .completed {
    font-size: 2px;
  }
  
@media (min-width: 770px) {
  #task {
    background-color: rgb(94, 156, 58);
  }
}

}
</style>
