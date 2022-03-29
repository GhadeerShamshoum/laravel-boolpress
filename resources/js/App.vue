<template>
  <div class="bgColor">
      <Header/>
      <Main/>
      <Footer/>

  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';
export default {
    name: "App",

    components: {
        Header,
        Main,
        Footer
    }
}
</script>

<style lang="scss" scoped>
.bgColor{
    background-color: rgb(214, 211, 211);
    min-height: 100vh;
}


</style>