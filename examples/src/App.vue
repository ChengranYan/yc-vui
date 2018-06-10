<template lang="pug">
    //- <v-icon name="arrow-left" size="12"></v-icon>
    modal(
      name="arrow-left" size="12"
    ) 
</template>

<script>
import 'highlight.js/styles/atom-one-dark.css'

import navConfig from './nav.config.json'
import PageHeader from './components/page-header'
import SideNav from './components/side-nav'
import FooterNav from './components/footer-nav'

export default {
  name: 'App',
  components: {
    PageHeader,
    SideNav,
    FooterNav
  },
  data () {
    return {
      navConfig: navConfig
    }
  }
}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
