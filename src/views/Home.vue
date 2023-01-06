<template>
  <Banner />
  <div class="main-container">
    <CardsOne />
    <CardsTwo />
    <br>
    <h1>Monte a sua pizza:</h1>
    <PedidoForm class="PedidoForm" />
  </div>
</template>

<script>

  import Banner from '../components/Banner.vue';
  import CardsOne from '../components/CardsOne.vue';
  import CardsTwo from '../components/Carrousel.vue';
  import PedidoForm from '../components/PedidoForm.vue';

  export default {
    name: "Home",
    components: {
      Banner,
      CardsOne,
      CardsTwo,
      PedidoForm
    }
  }

</script>

<style scoped>
  .PedidoForm{
    border-radius: 500px;
    background-color: rgb(51, 10, 10);
    padding: 120px;
    transition: 0.8s;
  }

  .PedidoForm:hover{
    background-color: rgb(224, 224, 224);
  }

  h1{
    font-weight: 800;
    letter-spacing: 2px;
    color: rgba(77, 8, 8, 0.945);
  }

  @media (max-width: 900px){
    .PedidoForm{
    border-radius: 0px;
    background-color: rgb(240, 240, 240);
    padding: 10px;  
  }
  }
</style>