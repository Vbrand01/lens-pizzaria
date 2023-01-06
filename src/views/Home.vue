<template>
  <Banner />
  <div class="main-container">
    <CardsOne />
    <Faixa />
    <CardsTwo />
    <!-- <PedidoForm class="PedidoForm" /> -->
  </div>
</template>

<script>

  import Faixa from '@/components/Faixa.vue';
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
    PedidoForm,
    Faixa
}
  }

</script>

<style scoped>
  .PedidoForm{
    border-radius: 20px;
    background-color: transparent;
    padding: 120px;
    transition: 0.8s;
  }

  .PedidoForm:hover{
    background-color: rgb(241, 241, 241);
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