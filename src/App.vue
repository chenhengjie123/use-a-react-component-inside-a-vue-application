<template>
  <div id="app">Who do you want to say hello to?
    <br>
    <input v-model="name">
    <hr>
    <HelloVue :name="name"/>
    <hr>
    <HelloReact :name="name"/>

    <p v-if="seen">现在你看到我了</p>
    <ol>
      <li v-for="todo in todos" v-bind:key="todo">
        {{ todo.text }}
      </li>
    </ol>
    
    <p>{{ message }}</p>
    <input v-model="message">
    <button v-on:click="reverseMessage">反转消息</button>

    <p>组件化todo-item</p>
    <ol>
      <ToDoItem
        v-for="item in groceryList"
        v-bind:todo="item"
        v-bind:key="item.id"
      ></ToDoItem>
    </ol>
  </div>
</template>

<script>
import HelloVue from "./components/HelloVue";
import HelloReact from "./components/HelloReact.jsx";
import ToDoItem from "./components/ToDoItem"

export default {
  name: "App",
  components: {
    HelloVue,
    HelloReact,
    ToDoItem
  },
  data() {
    return { 
      name: "World" ,
      seen: true,
      todos: [
        {text: 'js'},
        {text: 'vue'},
        {text: 'todo'}
      ],
      message: '1 2 3 4 5 6',
      groceryList: [
        { id: 0, text: '蔬菜' },
        { id: 1, text: '奶酪' },
        { id: 2, text: '随便其它什么人吃的东西' }
      ]
      };
  },
  methods: {
    reverseMessage: function() {
      this.message = this.message.split('').reverse().join('')
    }
  }
};
</script>