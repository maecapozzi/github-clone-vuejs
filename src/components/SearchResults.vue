<template>
  <div>
    <ul>
      <li v-for="repo in repoList">
        <md-card>
          {{ repo.name }}
        </md-card>
      </li>
    </ul>
  </div>
</template>

<script>
import 'babel-polyfill'
import Vue from 'vue'
import { MdCard } from 'vue-material/dist/components'
import 'vue-material/dist/vue-material.min.css'

Vue.use(MdCard)

export default {
  name: 'SearchResults',
  props: ['repoList'],
  data () {
    return {}
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
</style>
