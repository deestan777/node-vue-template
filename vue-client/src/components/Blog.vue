<template>
  <div class="hello">
  <h1>Blog</h1>
  <p class="lead">{{fetch_status}}</p>
  </div>
</template>

<script>
import axios from 'axios';
import response from "core-js/internals/is-forced";
export default {
  name: 'Blog',
  data() {
    return {
      fetch_status: 'Fetching data from server...',
    }
  },
  created () {
  axios({
    method: 'get',
    url: 'http://localhost:9000/',
  })
      .then((response) => {
        this.fetch_status = 'Data fetched from server: ' + response.data
      })
      .catch((error) => {
        this.fetch_status = 'Error fetching data from server: ' + error
      })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
