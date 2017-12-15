
<template>
  <div>
    <nav>
      <h1>{{ msg }}</h1>
      <ul>
        <form>
          <input class='search' />
          <button>Submit</button>
        </form>
      </ul>
    </nav>
    <ul v-if="repos.length">
      <li v-for="repo in repos">
        {{ repo.name }}
      </li>
    </ul>
    <p v-else>No repos left!</p>
  </div>

</template>

<script>
import axios from 'axios'

export default {
  name: 'SearchBar',
  data () {
    return {
      msg: 'Github',
      repos: [],
      errors: []
    }
  },
  created () {
    axios.get('https://api.github.com/users/maecapozzi/repos')
      .then(response => {
        const reposArray = []
        response.data.map(repo => {
          reposArray.push(repo)
        })
        this.repos = reposArray
        console.log(this.repos)
      })
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
