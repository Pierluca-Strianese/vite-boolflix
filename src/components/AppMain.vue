<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";
export default {
    name: 'Main',
    components: {
        AppCard
    },
    data() {
        return {
            store
        }
    }
}
</script >

<template>
    <AppHeader @searchRequest="requestToAPI" />
    <div class="container">

        <h1 class="text-white mb-3">Film</h1>
        <div class="row row-cols-6">
            <AppCard v-for="movie in store.movieResultArray" :key="movie.id" :image="movie.poster_path"
                :titleOriginal="movie.original_title" :titleTranslated="movie.title" :language="movie.original_language"
                :vote="Math.ceil(movie.vote_average / 2)" />
        </div>

        <h1 class="text-white mb-3">Serie TV</h1>
        <div class="row row-cols-6">
            <AppCard v-for="serie in store.seriesResultArray" :key="serie.id" :image="serie.poster_path"
                :titleOriginal="serie.original_name" :titleTranslated="serie.name" :language="serie.original_language"
                :vote="Math.ceil(serie.vote_average / 2)" />
        </div>
    </div>
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap";

.container {
    padding: 10rem 0;
}

h1 {
    font-size: 60px;
}
</style>