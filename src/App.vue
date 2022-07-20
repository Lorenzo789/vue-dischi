<template>
  <div id="app">
    <Header @search="filterCard"/>
    <Main />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  methods: {
    filterCard(selectGenre){
      console.log('hai selezionato');
    }
  }
}
</script>

<style lang="scss">

  @import'./styles/general.scss';
  @import'./styles/variables.scss';
  @import'../node_modules/bootstrap-icons/font/bootstrap-icons.css';

</style>
