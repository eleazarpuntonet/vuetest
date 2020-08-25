<template>
  <div id="app">
    <landing-page>
    </landing-page>
  </div>
</template>

<script>
import LandingPage from './components/LandingPage'

export default {
  name: 'App',
  components: {
    LandingPage
  }
}
</script>

<style lang="sass">
@media (max-width: 360px)
  .app
    padding: 10px
    background-color: red !important
</style>
