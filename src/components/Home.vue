
<template>
  <div>
    <h1>{{ msg }}</h1>
    <SearchBar />
  </div>

</template>

<script>
  import SearchBar from './SearchBar'
  import SearchInput from './SearchInput'

  export default {
    name: 'Home',
    components: {
      SearchBar,
      SearchInput
    },
    data () {
      return {
         msg: 'Github'
      }
    }
  }

</script>

<style scoped>

</style>
