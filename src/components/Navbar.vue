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
        <!-- <li class="nav-item">
            <router-link class="navbar-brand" to="/"></router-link>
        </li>     -->
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
        height: 115px; /* defina uma altura */
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        align-items: center;
        display: flex;
        justify-content: space-between;
        z-index: 10;
    }


    @media (max-width: 575px){
      .navbar-nav{
        display: flex;
        justify-content: flex-end;
        align-items: left;
        gap: 15px;
        background: rgba(53, 4, 2, 0.5);
        border-radius: 16px;
        box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
        backdrop-filter: blur(7.9px);
        -webkit-backdrop-filter: blur(7.9px);        
        padding: 15px;
        border-radius: 10px;        
      }
      .navbar-brand{
        padding: 10px;
        border-radius: 10px;
        color: rgb(255, 187, 0);
        font-weight: 700;
      }
    }

</style>