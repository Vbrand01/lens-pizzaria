<template>

    <nav class="navbar navbar-expand-sm background-nav navbar-dark">
  <div class="container-fluid">
    <router-link to="/" id="logo-url">
            <img :src="logo" :alt="alt" id="logo">
        </router-link>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#collapsibleNavbar">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="collapsibleNavbar">
      <ul class="navbar-nav">
        <li class="nav-item">
            <router-link class="navbar-brand" to="/">Home</router-link>
        </li>
        <li class="nav-item">
            <router-link class="navbar-brand" to="/pedidos">Pedidos</router-link>
        </li>
        <li class="nav-item">
            <router-link class="navbar-brand" to="/"></router-link>
        </li>    
      </ul>
    </div>
  </div>
</nav>

</template>


<script>

    export default {
        name: "Navbar",
        props: [
            "logo",
            "alt"
        ]
    }

</script>

<style scoped>

    #logo {
        width: 100px;
        height: 100px;
    }

    .background-nav{
        background-color: rgb(49, 6, 3);
    }

</style>