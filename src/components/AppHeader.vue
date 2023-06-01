<script>
import { store } from '../store';
export default {
    name: 'AppHeader',
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <header>
        <div class="head-container px-4 d-flex align-items-center justify-content-between">
            <img class="logo" src="../../public/logo-boolflix.png" alt="logo">
            <div class="cont-input me-2 d-flex">
                <button class="btn btn-outline-danger me-2"
                    @click="$emit('searchMovie'), $emit('searchSeries')">Cerca</button>
                <input v-model="store.movieSearchTitle" @keyup.enter="$emit('searchMovie'), $emit('searchSeries')"
                    class="form-control" type="text" placeholder="Cerca un film">
            </div>
        </div>
    </header>
</template>


<style lang="scss" scoped>
@use '../style/general.scss' as *;

.head-container {
    background-color: #141414;
    height: 80px;
    width: 100%;
    position: fixed;
    z-index: 999;

    .logo {
        height: 65px;
        object-fit: contain;

    }
}
</style>

