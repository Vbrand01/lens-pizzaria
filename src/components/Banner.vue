<template>
    <div id="main-banner">
        <h1>Lens Pizzaria</h1>
        <!-- <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Accusantium velit earum amet aliquid est obcaecati eos placeat ex corrupti. Nostrum distinctio cupiditate sed in quo beatae expedita impedit nemo tempore?</p> -->
        <!-- <img src="../../public/img/3d.png" alt=""> -->
    </div>
</template>

<script>
    export default {
        name: "Banner"
    }
</script>

<style scoped>
    #main-banner{
        background-image: url('../../public/img/pizzahome.png');
        background-position: 0 -250px;
        background-size: cover;
        height: 700px;
        display: flex;
        align-items: center;
        justify-content: flex-start;
    }

    #main-banner h1{
        color: rgb(221, 221, 221);
        text-align: center;
        font-size: 60px;
        background-color: rgb(128, 1, 1);
        padding: 20px 40px;
        border-radius: 8px;
        margin: 200px;
    }
</style>