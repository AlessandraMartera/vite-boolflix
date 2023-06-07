<script>
import axios from 'axios'
import { store } from './store.js'
import AppHeader from './components/AppHeader.vue'
import AppSearch from './components/AppSearch.vue'
import CardList from './components/cardList.vue'

export default {
  components: {
    AppHeader,
    CardList
  },

  // star data
  data() {
    return {
      store
    }
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
    }
  },
  created() {
    this.getInfoMovie();
    this.getInfoTv();
  }

}
</script>

<template>
  <AppHeader />
  <main>
    <CardList />
  </main>
</template>

<style lang="scss"></style>
