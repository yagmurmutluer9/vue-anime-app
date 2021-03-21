<template>

<div class="animelist">
  <Anime v-for="anime in animes" :key="anime.id" :anime="anime"/>
</div>

</template>

<script>

import Anime from '@/components/Anime.vue'
export default {

    components: {
        Anime
    },
    props: ["animes"]

}
</script>

<style>

.animelist {
margin: 10px;
justify-content: space-between;
display: flex;
flex-wrap: wrap;

}

</style>