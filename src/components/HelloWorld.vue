<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{info}}</h1>
    <ul id="example-1">
    <h1>idEmpleado</h1>
   <li v-for="p in prueba" v-bind:key="p.idEmpleado">
   {{ p.idEmpleado }}
  </li>
  <br>
 <h1>Nombre</h1>
   <li v-for="p in prueba" v-bind:key="p.nombre">
    {{ p.nombre }}
  </li>
  <br>
  <h1>Apellido</h1>  <li v-for="p in prueba" v-bind:key="p.apellido">
  {{ p.apellido }}
  </li>
  <br>
  <h1>DPI</h1>
  <li v-for="p in prueba" v-bind:key="p.dpi">
  {{ p.dpi }}
  </li>
  <br>
  <h1>Email</h1>
  <li v-for="p in prueba" v-bind:key="p.email">
    {{ p.email }}
  </li>
</ul>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="http://localhost:3000/prueba" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <button @click="getinfo">Click</button>
  </div>
</template>

<script>

const axios = require('axios');

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }, 
data(){
  return {
    info: "esperando info...",
  prueba: []
  }
},

methods: {
  getinfo(){
    axios.get('http://localhost:3000/prueba')
  .then((response)=> {
        // eslint-disable-next-line  
    console.log(response);
    this.prueba = response.data;

  })
  .catch(function (error) {
    // eslint-disable-next-line
    console.log(error);
  });
  }
}
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
