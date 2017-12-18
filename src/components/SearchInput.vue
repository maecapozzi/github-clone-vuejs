<template>
  <form>
    <input v-model='username' placeholder='enter a username' class='search' />
    <button @click='getRepos($event, username)'>Submit</button>
  </form>
</template>

<script>
import axios from 'axios'

export default {
  name: 'SearchBar',
  props: ['getRepos'],
  data () {
    return {
      repos: [],
      errors: [],
      username: ''
    }
  },
}

</script>

<style scoped>
h1, h2 {
  font-weight: normal;
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

.navbar {
  background-color: #24292F;
  height: 60px;
}
</style>
