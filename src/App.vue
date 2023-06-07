<script>
import axios from 'axios'
import { store } from './store.js'
import AppHeader from './components/AppHeader.vue'
import CardList from './components/cardList.vue'
import AppSearch from './components/AppSearch.vue'

export default {
  components: {
    AppHeader,
    AppSearch,
    CardList,
  },

  // star data
  data() {
    return {
      store
    };
  },

  // start methods
  methods: {
    getInfoMovie() {
      let searchUrlMovie = store.apiUrlMovie + store.titleSearched;
      axios.get(searchUrlMovie)
        .then(ref => {
          store.cardListMovie = ref.data.results;
          console.log(store.cardListMovie);
        }
        )
    },
    getInfoTv() {
      let searchUrlTv = store.apiUrlTv + store.titleSearched;
      axios.get(searchUrlTv)
        .then(ref => {
          store.cardListTv = ref.data.results;
          console.log(store.cardListTv);
        }
        )
    },
    getCards() {
      this.getInfoMovie();
      this.getInfoTv();
    }
  },
  created() {
    this.getCards();
  }
}
</script>

<template>
  <AppHeader @search="getCards" />
  <main>
    <CardList />
  </main>
</template>

<style lang="scss"></style>
