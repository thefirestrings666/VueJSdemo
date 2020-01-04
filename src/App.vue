<template>
  <div id="app">
    <TopBar/>
    <MainContent/>
  </div>
</template>

<script>
import TopBar from './components/topBar'
import MainContent from './components/MainContent'


export default {
  name: 'App',
  components: {
    TopBar,
    MainContent
    
  },
  data () {
    return {
    }
  },

}
</script>






<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0rem;
  padding: 0rem;
}

</style>
