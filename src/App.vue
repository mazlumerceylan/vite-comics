<template>
  <div id="app">
    <Navbar />
    <Main />
    <Footer />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Main from "./components/Main.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    Navbar,
    Main,
    Footer,
  },
};
</script>

<style lang="scss">
@import './assets/scss/header.scss';
@import './assets/scss/main.scss';
@import './assets/scss/footer.scss';

body {
  font-family: 'Roboto', sans-serif;
}
</style>
