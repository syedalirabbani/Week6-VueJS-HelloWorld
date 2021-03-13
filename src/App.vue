<template>
  <div id="app">
    <h1>hello world</h1>
    <p>welcome to VueJS project</p>
    <p>hello {{name}}. you are {{age}} years old. I am from {{location}}</p>
    <p>testing operation : {{num1}} + {{num2}} = {{num1+num2}}</p>
    <button v-on:click="sayHello">click me!</button>
    <hr>
    <h2>counter</h2>
    <p id="count" >{{counter}}</p>
    <p>{{message}}</p>
    <button v-on:click="inc">increment</button>
    <button v-on:click="dec">decrement</button>
    <button v-on:click="res">reset</button>
    <hr>
    <input type="text" placeholder="enter your name" v-model="username"><button v-on:click="pressMe">press me</button>
    <p>{{message2}} </p>  
    <hr>
    <input type="text" placeholder="enter your item" v-model="newtodo">
    <button v-on:click="addItem">Add new item</button>
    <ul>
      <li v-for="todo in todos" :key="todo">{{todo}}</li>
    </ul>
    <hr>
    <p v-if="gender=='male'"> Hello Mr {{name}}</p>
    <p v-if="gender=='female'"> Hello Ms {{name}}</p>
  </div>
</template>

<script>

//----------------------------------------//

export default {
  name: 'App',
  data() {
    return {
      name:"Ali",
      age:30,
      location:"johor",
      num1:10,
      num2:3,
      counter:0,
      message:"",
      message2:"",
      username:"",
      newtodo:"",
      todos:["makan","minum","tidur"],
      gender:"male"
    }
  },
  methods: {
    addItem:function(){
      this.todos.push(this.newtodo);
    },

    sayHello:function(){
      alert("Hello "+this.name);
    },
    inc:function(){
        this.message=""
        this.counter++;
    },

    dec:function(){
     
      if (this.counter == 0){
        this.message = "Number cannot be negative"
      }
      else {
        this.counter--;
    }


    },

    res:function(){
      this.counter=0;
      this.message=""
    },

    pressMe:function(){
      this.message2="Hello "+this.username;

    }

    


  }

  
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
