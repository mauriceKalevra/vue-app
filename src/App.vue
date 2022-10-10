<template>
<div id="app">
{{name}},
{{age}},
{{ `${height} ${IQ}` }} <hr>
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
</div>
</template>

<script>

export default {
  name: 'App',
  data: () =>({
    name: 'Mauricee',
    age: 185,
    height: 183,
    IQ: 138,
    Cock: 16
  }),
  computed: {
    fullid() {
      return this.name + " " + this.age;
    }
  }
}
</script>

<style>
.agee {
  border: 2px solid #f00;
  margin: 5px;
  padding: 10px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
