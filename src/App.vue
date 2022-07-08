<template>

  <Start />
  <Partners />
  <Team />
  <Contacts />
  <Footer />
</template>

<script>
import Header from './components/Header.vue'
import Start from './components/Start.vue'
import Partners from './components/Partners.vue'
import Team from './components/Team.vue'
import Contacts from './components/Contacts.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Start,
    Partners,
    Team,
    Contacts,
    Footer,
  }
}
</script>

<style lang="scss">
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  body {
    font-family: 'Ubuntu', sans-serif;
  }
  .box {
    padding: 0 20px;
    max-width: 1240px;
  }
</style>
