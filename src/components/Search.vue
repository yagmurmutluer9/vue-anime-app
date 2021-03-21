<template>
  <input type="text" placeholder="search for an anime..." v-model="search" @input="onSearch"  > 
</template>

<script>
export default {

    data() {

        return {
            search: '',
            timeout: null
        }
    },
    methods: {
        onSearch() {
        clearTimeout(this.timeout);
        this.timeout = setTimeout(() => {
        this.searchAnime();
      }, 500)

        },
        searchAnime(){
            fetch(`https://api.jikan.moe/v3/search/anime?q=${this.search}&limit=12`)
            .then(response => response.json())
            .then(result => {
                this.$emit('fetched-result', result)
            } )
        }
    }

}
</script>

<style>

input {
width: 100%;
padding: 10px;
font-size: 18px;
border: 2px solid black;
background-color:rgb(6, 48, 48);
color:white
}

input::placeholder {
color:white;
}

input:focus {
background-color: rgb(13, 82, 82);}

</style>