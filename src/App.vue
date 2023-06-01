<script>
import axios from "axios";
import { store } from './store';
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";


export default {
  name: "App",
  components: {
    AppHeader,
    AppMain,
  },
  data() {
    return {
      store
    }
  },
  methods: {
    getApi() {
      axios.get(store.apiUrl, {
        params: {
          query: store.movieSearchTitle
        }
      })
        .then(result => {
          store.movieResultArray = result.data.results;
          console.log(store.movieResultArray);
        })
    },
    getApiSeries() {
      axios.get(store.apiUrlSeries, {
        params: {
          query: store.movieSearchTitle
        }
      })
        .then(result => {
          store.seriesResultArray = result.data.results;
          console.log(store.seriesResultArray);
        })
    }
  },
  mounted() {
    this.getApi();
    this.getApiSeries();
  }
}
</script>

<template>
  <AppHeader @searchMovie="getApi" @searchSeries="getApiSeries" />
  <AppMain />
</template>


<style lang="scss">
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #141414;
}
</style>
