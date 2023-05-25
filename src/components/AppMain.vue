<script>

import ResultList from './ResultList.vue';
import { store } from '../store'

export default {
    data() {
        return {
            store,
        }
    },

    components: {
        ResultList
    }
};

</script>

<template>
    <ResultList listTitle="Risultati dei film" :arrCards="store.arrMovies" />
</template>

<style lang="scss" scoped></style>