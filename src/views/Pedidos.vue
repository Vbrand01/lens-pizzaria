<template>
  <div class="main-container">
    <!-- <PedidoForm />
    <Reload /> -->
    <Dashboard />
  </div>
</template>

<script>
import Dashboard from '@/components/Dashboard.vue';
import PedidoForm from '@/components/PedidoForm.vue';
import Reload from '@/components/Reload.vue';

  export default {
    name: "Pedidos",
    components: {
    Dashboard,
    PedidoForm,
    Reload
}
}

let url = "http://localhost:3000/sabores";

console.log()
</script>

<style scoped>
.main-container{
  margin-top: 150px;
}

h1{
  font-weight: 800;
  text-transform: uppercase;
  letter-spacing: 10px;
}

@media (max-width: 700px){
  h1{
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0px;
    font-size: 32px;
  }
}
</style>