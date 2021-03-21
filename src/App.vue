<template>
<Header/>
<search  @fetched-result="onResultFetched"/>
<AnimeList :animes="animes"/>

</template>

<script>
import AnimeList from './components/AnimeList.vue'
import Search from './components/Search.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    AnimeList,
    Search,
    Header
  },
  data() {
    return {
      animes: []
    }
  },
  methods: {
     onResultFetched(result) {
        console.log(result);
        this.animes = result.results;
     }
  }
}
</script>

<style>

* {
  box-sizing: border-box;
}
body {
  padding: 50px;
  background:rgba(13, 82, 82, 0.459);
}
#app {
  width: 800px;
  margin: 0 auto;
}

</style>
