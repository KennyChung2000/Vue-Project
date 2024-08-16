<script>
import ToDoItem from "./components/ToDoItem.vue";
import ToDoForm from "./components/ToDoForm.vue";
import uniqueId from "lodash.uniqueid";
export default {
  name: "app",
  components: {
  ToDoItem,ToDoForm
  },
  data() {
    return {
      ToDoItems: [
        { id: uniqueId("todo-"), label: "Learn Vue", done: false,name:uniqueId("name-") },
        {
          id: uniqueId("todo-"),
          label: "Create a Vue project with the CLI",
          done: true,
          name:uniqueId("name-")
        },
        { id: uniqueId("todo-"), label: "Have fun", done: true,name:uniqueId("name-") },
        { id: uniqueId("todo-"), label: "Create a to-do list", done: false,name:uniqueId("name-") },
      ],
    };
  },
  methods: {
    addToDo(toDoLabel,toDoName) {
      this.ToDoItems.push({id:uniqueId('todo-'), label: toDoLabel,name:toDoName ,done: false});
    }
  },
};
</script>

<template>
  
  <!--<HelloWorld msg="Welcome to Your Vue.js App" /> -->

  
  <div id="app">
    <h1>My To-Do List</h1>

    <to-do-form @todo-added="addToDo"></to-do-form>

    <table border="1">
      <thead>
        <tr>
          <th scope="col" style="width: 20%;">DONE</th>
          <th scope="col" style="width: 20%;">LABEL</th>
          <th scope="col" style="width: 20%;">NAME</th>
           <th scope="col" style="width: 20%;">START DATE</th>
           <th scope="col" style="width: 20%;">END DATE</th>
        </tr>
      </thead>
      <tbody v-for="item in ToDoItems" :key="item.id">
        <to-do-item
          :label="item.label"
          :done="item.done"
          :id="item.id"
          :name="item.name"
          :startDate="item.startDate"
          :endDate="item.endDate">
        </to-do-item>

      </tbody>
    </table>

    <!--<ul>
      <li v-for="item in ToDoItems" :key="item.id">
        <to-do-item
          :label="item.label"
          :done="item.done"
          :id="item.id"
          :id="item.id"></to-do-item>
      </li>
    </ul>-->

  </div>

     
</template>

<style scoped>
</style>
