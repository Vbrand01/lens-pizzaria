<template>
  <Banner />
  <div class="main-container">
    <CardsOne />
    <CardsTwo />
    <br>
    <h1>Monte a sua pizza:</h1>
    <PizzaForm />
  </div>
</template>

<script>

  import Banner from '../components/Banner.vue';
  import CardsOne from '../components/CardsOne.vue';
  import CardsTwo from '../components/Carrousel.vue';

  import PizzaForm from '../components/PizzaForm.vue';


  export default {
    name: "Home",
    components: {
      Banner,
      CardsOne,
      CardsTwo,
      PizzaForm
    }
  }

</script>
