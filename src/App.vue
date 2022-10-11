<template>
<div id="app">
<div class="title">
Vue-js Application
</div>
Name: {{name}},
Alter:  {{age}},
Größe: {{ `${height} IQ: ${IQ}` }} <hr>
{{fullid}}
<hr>
{{age >18 ? 'adult' : 'kid' }},
<div class="agee">
{{age}}
<span v-if="age < 18">
You're under 18.
</span>
<span v-else-if="age ==18">
You're 18 years old
</span>
<span v-else>
Passed, You're above 18 years old!
</span>
</div>
<div v-show="name == 'Maurice'">
Hi, Maurice!
</div>
<span v-if="age > 18">
Matured!
</span>
<span v-else>
You're to young for this information!
</span>
<p v-for="n in 3" v-bind:key="n">
{{n}}
</p>  
<ul>
<li v-for="(todo, index) in todos" v-bind:key="todo.id"
:class="{'finishedTask':todo.finished}">
{{++index}}.{{todo.name}}
<input type="checked" checked v-if="finished" />
<input type="checkbox" :checked="todo.finished" />
<a :href="'?id='+todo.id">show</a>
</li>
</ul>
<!-- statt v-on geht auch @ -->
<button v-on:click="submit">Submit</button>
</div>
</template>

<script>
export default {
  name: 'App',
  data: () =>({
    name: 'Maurice',
    age: 19,
    height: 183,
    IQ: 138,
    hometown: 'Freiburg',
    todos: [
      {id:1, finished: true, name: "Vue lernen"},
      {id:2, finished: true,  name: "git pushen"},
      {id:3, finished: false, name: "Datenbanken integrieren"}
    ]
  }),
  methods: {
    submit() {
      alert("submit");
    }
  },
  computed: {
    fullid() {
      return this.name + " " + this.age + " " + this.height + " " + this.IQ + " " +  this.hometown;
    }
  }
}
</script>

<style>

.finishedTask {
  text-decoration: line-through;
}
.title {
  border: 2px blue;
  margin: 2px;
  padding: 5px;
  text-align: center;
  font-size: 50;
}
.agee {
  border: 2px solid #f00;
  margin: 5px;
  padding: 10px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
