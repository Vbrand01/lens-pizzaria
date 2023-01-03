<template>

  <Navbar :logo="logo_src" :alt="app_name" />
  <router-view />
  <Footer />

</template>

<script>

  import Navbar from './components/Navbar.vue';
  import Footer from './components/Footer.vue';

  export default {
    components: {
      Navbar,
      Footer
    },

    data(){
      return {
        logo_src: "/img/logo.png",
        app_name: "Lens Pizzaria"

      }
    }

  }


</script>

<style>

  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Monoton&family=Russo+One&family=VT323&display=swap');

  *{
    font-family: 'Inter', sans-serif;
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  .main-container{
    margin: 100px;
    min-height: 250px;
  }

  h1{
    text-align: center;
    font-size: 42px;
    margin-bottom: 30px;
    color: #222
  }

</style>
