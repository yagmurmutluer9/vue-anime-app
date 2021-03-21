<template>
<div class="card">
<div class="img-anime" :style="`background-image:url('${anime.image_url}')`"></div>

<a :href="anime.url" target="_blank"> 
			<h3>{{ anime.title }}</h3>
        </a>
			<h4> episodes: {{ anime.episodes }}</h4>

        <p> {{anime.synopsis}}</p>

</div>
</template>

<script>
export default {

    props: ["anime"]

}
</script>

<style>

.img-anime {
  width: 240px;
  height: 240px;
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}

.card {
	flex: 1 1 33%;
	width: 33%;
	max-width: 33%;
	padding: 0px 8px;
	margin-bottom: 8px; }




</style>