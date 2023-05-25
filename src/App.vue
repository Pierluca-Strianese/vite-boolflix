<script>

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import ResultList from './components/ResultList.vue';
import AppCard from './components/AppCard.vue';
import axios from 'axios';
import { store } from './store';

export default {
  components: { AppHeader, AppMain, ResultList, AppCard },

  methods: {
    requestToAPI(searchStr) {
      axios
        .get('https://api.themoviedb.org/3/search/movie', {
          params: {
            api_key: 'e6b2bdbe301aaaad8a0bf3b9509fbec6',
            query: searchStr,
          },
        })
        .then(response => response.data);
    }
  },
};
</script >

<template>
  <AppHeader @searchRequest="requestToAPI" />
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap";
</style>
