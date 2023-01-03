<template>
    <div id="nav">
        <router-link to="/" id="logo-url">
            <img :src="logo" :alt="alt" id="logo">
        </router-link>
        <router-link to="/">Home</router-link>
        <router-link to="/pedidos">Pedidos</router-link>
    </div>
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

    #nav{
        background-color: rgb(105, 10, 7);
        border-bottom: 4px solid rgb(255, 38, 0);
        padding:  15px 30px;
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        /* position: fixed;
        z-index: 10; */
    }

    #nav #logo-url{
        margin: auto;
        margin-left: 0;
    }

    #logo {
        width: 100px;
        height: 100px;
    }

    #nav a {
        color: rgb(255, 187, 0);
        font-weight: 800;
        letter-spacing: 1px;
        text-decoration: none;
        margin: 12px;
        transition: .5s;
    }

    #nav a:hover{
        color: #FFF;
    }

</style>