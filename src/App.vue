<template>
  <!-- <Start />
  <Partners /> -->
  <Team />
  <Contacts />
  <Footer />
</template>

<script>
import Start from './components/Start.vue'
import Partners from './components/Partners.vue'
import Team from './components/Team.vue'
import Contacts from './components/Contacts.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
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
  html {
    scroll-behavior: smooth;
  }
  body {
    font-family: 'Ubuntu', sans-serif;
  }
  .box {
    padding: 0 20px;
    max-width: 1440px;
  }
  .hidden {
    overflow: hidden;
  }
  .active-block {
  transform: translate(0, 0);
  transition: 500ms;
  }
  .deactive-block {
  transform: translate(0, -2000%);
  transition: 500ms;
  }
</style>
