<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <button @click="getinfo" >Click</button>
  </div>
</template>

<script>

const axios = require('axios');

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }, 

methods: {
  getinfo(){
    axios.get('http://localhost:3000/users')
  .then(function (response) {
        // eslint-disable-next-line  
    console.log(response);
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
