<script>
import axios from 'axios'
import { store } from './store.js'
import AppHeader from './components/AppHeader.vue'


export default {
  components: {
    AppHeader
  },

  // star data
  data() {
    return {
      store
    }
  },

  // start methods
  methods: {

  }
}
</script>

<template>
  <AppHeader />
</template>

<style lang="scss"></style>
