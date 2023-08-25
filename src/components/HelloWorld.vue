<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    
    <button v-on:click="sendRequest">백엔드 요청</button>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods:{
    sendRequest(){
      console.log("button clicked.");

      axios.get('http://54.176.66.104')
      .then(response => {
        console.log("public ip.");
        console.log(response.data);
      })
      .catch(error => {
        console.log("public ip.");
        console.error('Error fetching data:', error);
      });

      axios.get('http://172.31.3.139')
      .then(response => {
        console.log("private ip.");
        console.log(response.data);
      })
      .catch(error => {
        console.log("private ip.");
        console.error('Error fetching data:', error);
      });

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
