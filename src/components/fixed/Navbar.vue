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

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Kaushan+Script&family=Monoton&family=Russo+One&family=VT323&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Kaushan+Script&family=Luckiest+Guy&family=Monoton&family=Russo+One&family=VT323&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Kaushan+Script&family=Luckiest+Guy&family=Monoton&family=Passion+One:wght@400;700;900&family=Russo+One&family=VT323&display=swap');

    #logo {
        width: 100px;
        height: 100px;
    }


    .background-nav{
        background-color: rgba(77, 8, 8, 0.945);
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

    .navbar-brand{
      float: left;
      font-weight: 800;
      letter-spacing: 1px;
      font-size: 25px;
      color: rgb(243, 207, 1);
      background-color: transparent;
      padding: 15px;
      border-radius: 8px;
      transition: 1s;
      border-bottom: 3px solid transparent;
    }

    .navbar-brand:hover{
      background-color: rgb(250, 6, 46);
    }

    .navbar-brand:active{
      border-bottom: 3px solid red !important;
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