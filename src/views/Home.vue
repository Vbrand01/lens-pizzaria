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
  import PizzaForm from '../components/PizzaForm.vue';
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
    border-radius: 500px 500px 20px 20px;
    background-color: rgb(51, 10, 10);
    padding: 100px;
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