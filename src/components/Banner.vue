<template>
    <div id="main-banner">
        <div class="container">
            <div class="row" id="content">
                <div class="col-sm-6" id="bloco1">
                    <div class="title-logo">
                        <h1><img src="../../public/img/logo.png" height="100px" alt="">Pizzaria Lens</h1>
                    </div>
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Officiis fuga temporibus error odio
                        sunt! Voluptates asperiores consectetur cumque, impedit distinctio, ad officiis perspiciatis
                        vitae harum aperiam odio veniam quae sequi.</p>
                    <div class="alinhando-button">
                        <a href="#pedidosHome"><button class="btoFazerPedido">
                                <span>Fazer um pedido</span>
                                <svg viewBox="0 0 13 10" height="10px" width="15px">
                                    <path d="M1,5 L11,5"></path>
                                    <polyline points="8 1 12 5 8 9"></polyline>
                                </svg>
                            </button></a>
                    </div>
                </div>
                <div class="col-sm-6">
                    <img class="img3d" src="../../public/img/men.png" alt="">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Banner"
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Kaushan+Script&family=Monoton&family=Russo+One&family=VT323&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Kaushan+Script&family=Luckiest+Guy&family=Monoton&family=Russo+One&family=VT323&display=swap');

#main-banner {
    background-image: url('../../public/img/pizzahome10.png');
    /* background: linear-gradient(90deg, rgb(0, 0, 0) 0%, rgb(150, 90, 1) 43%, rgba(255,0,0,1) 100%); */
    /* background-position: 0 -250px; */
    background-size: cover;
    display: flex;
    align-items: center;
    justify-content: flex-start;
    min-height: 700px;
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    padding: 10px;
}

#bloco1 {
    color: rgb(221, 221, 221);
    text-align: center;
    background: rgba(0, 0, 0, 0.705);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5.9px);
    -webkit-backdrop-filter: blur(5.9px);
    padding: 40px;
    border-radius: 20px;
    height: 100%;
    margin-top: 180px;
    margin-bottom: 100px;
}

#bloco1 h1 {
    color: rgb(221, 221, 221);
    text-align: center;
    font-weight: 800;
    letter-spacing: 6px;
    font-size: 64px;
    background-color: rgba(82, 82, 82, 0.349);
    border-radius: 8px;
    padding: 10px;
}

.alinhando-button {
    display: flex;
    align-items: center;
    justify-content: center;
}

.img3d {
    margin-top: 90px;
    width: 100%;
}


a {
    text-decoration: none;
}

.btoFazerPedido {
    position: relative;
    margin: auto;
    padding: 18px 180px;
    transition: all 0.2s ease;
    height: 75px;
    border: none;
    background-color: rgb(250, 6, 46);
    border-radius: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100% !important;
}

.btoFazerPedido:before {
    content: "";
    position: absolute;
    top: 0;
    height: 75px;
    left: 0;
    display: block;
    border-radius: 10px;
    background: rgb(255, 187, 0);
    width: 45px;
    transition: all 0.3s ease;
}

.btoFazerPedido span {
    position: relative;
    font-family: "Ubuntu", sans-serif;
    font-size: 18px;
    font-weight: 700;
    letter-spacing: 0.05em;
    color: rgb(255, 187, 0);
}

.btoFazerPedido svg {
    position: relative;
    top: 0;
    margin-left: 10px;
    fill: none;
    stroke-linecap: round;
    stroke-linejoin: round;
    stroke: rgb(255, 187, 0);
    stroke-width: 2;
    transform: translateX(-5px);
    transition: all 0.3s ease;
}

.btoFazerPedido:hover:before {
    width: 100%;
    background: rgb(0, 133, 51);
}

.btoFazerPedido:hover svg {
    transform: translateX(0);
}

.btoFazerPedido:active {
    transform: scale(0.95);
}

/* @media (max-width: 768px){
    .img3d {
    margin-top: 20px;
    width: 100%;
    margin-bottom: 60px;
} */

@media (max-width: 995px) {
    .container {
        width: 100% !important;
    }
    .img3d {
    margin-top: 90px;
    width: 100%;
    }

    #bloco1 {
    color: rgb(221, 221, 221);
    text-align: center;
    background: rgba(0, 0, 0, 0.705);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5.9px);
    -webkit-backdrop-filter: blur(5.9px);
    padding: 40px;
    border-radius: 20px;
    height: 100%;
    margin-top: 180px;
    margin-bottom: 100px;
}
}

@media (max-width: 768px) {
    #content {
        flex-direction: column-reverse;
    }

    .img3d {
        margin-top: 100px;
        margin-bottom: -220px;
        width: 100%;
    }

    #bloco1 {
        margin-bottom: 100px;
    }

    #bloco1 h1 {
        color: rgb(221, 221, 221);
        text-align: center;
        font-weight: 800;
        letter-spacing: 6px;
        font-size: 15px;
        background-color: rgba(82, 82, 82, 0.349);
        border-radius: 8px;
        padding: 10px;
        display: non;
    }

    .btoFazerPedido {
    position: relative;
    margin: auto;
    padding: 18px 70px;
    transition: all 0.2s ease;
    height: 75px;
    border: none;
    background-color: rgb(250, 6, 46);
    border-radius: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100% !important;
    }


    .title-logo {
        flex-direction: column-reverse !important;
    }
}

p {
    font-size: 16px;
}

.btoFazerPedido span {
    flex-basis: 100%
}
</style>