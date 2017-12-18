<template>
  <div>
    <ul>
      <SearchInput v-bind='{getRepos}'></SearchInput>
    </ul>
    <SearchResults v-bind:repoList='repos'></SearchResults>
  </div>
</template>

<script>
import axios from 'axios'
import SearchInput from './SearchInput'
import SearchResults from './SearchResults'

export default {
  name: 'SearchBar',
  data () {
    return {
      repos: [],
      errors: [],
      username: ''
    }
  },
  components: {
    SearchInput,
    SearchResults
  },
  methods: {
    getRepos: function (event, username) {
      event.preventDefault()
      const url = 'https://api.github.com/users/' + username + '/repos' 
      axios.get(url)
      .then(response => {
        const reposArray = []
        response.data.map(repo => {
          reposArray.push(repo)
        })
        this.repos = reposArray
        return this.repos
      })
    }
  }
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
