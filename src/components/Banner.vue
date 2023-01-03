<template>
    <div id="main-banner">
        <div class="container">
            <div class="row">
                <div class="col-sm-8" id="bloco1">
                    <div>
                        <h1>Pizzaria Lens<img src="../../public/img/logo.png" height="100px" alt="">
                            </h1>
                    </div>
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Officiis fuga temporibus error odio
                        sunt! Voluptates asperiores consectetur cumque, impedit distinctio, ad officiis perspiciatis
                        vitae harum aperiam odio veniam quae sequi.</p>
                    <button class="cta">
                        <span>Gostaria de fazer um pedido</span>
                        <svg viewBox="0 0 13 10" height="10px" width="15px">
                            <path d="M1,5 L11,5"></path>
                            <polyline points="8 1 12 5 8 9"></polyline>
                        </svg>
                    </button>
                </div>
                <div class="col-sm-4">
                    <img class="img3d" src="../../public/img/3d.png" alt="">
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
    background-image: url('../../public/img/pizzahome.png');
    background-position: 0 -250px;
    background-size: cover;
    height: 700px;
    display: flex;
    align-items: center;
    justify-content: flex-start;
}

#bloco1 {
    color: rgb(221, 221, 221);
    text-align: center;
    background: rgba(53, 4, 2, 0.5);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(5.9px);
    -webkit-backdrop-filter: blur(5.9px);
    padding: 40px;
    border-radius: 20px;
    height: 100%;
    margin-top: 40px;
}

#bloco1 h1 {
    color: rgb(221, 221, 221);
    text-align: center;
    font-weight: 800;
    letter-spacing: 6px;
    font-size: 64px;
    background-color: rgba(8, 78, 17, 0.589);
    border-radius: 8px;
    padding: 10px;
    font-family: 'Luckiest Guy', cursive;

}

.img3d {
    margin-left: 100px;
}




.cta {
    position: relative;
    margin: auto;
    padding: 12px 180px;
    transition: all 0.2s ease;
    height: 75px;
    border: none;
    background-color: rgb(105, 10, 7);
    border-radius: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.cta:before {
    content: "";
    position: absolute;
    top: 0;
    height: 75px;
    left: 0;
    display: block;
    border-radius: 50px;
    background: rgb(255, 187, 0);
    width: 45px;
    transition: all 0.3s ease;
}

.cta span {
    position: relative;
    font-family: "Ubuntu", sans-serif;
    font-size: 18px;
    font-weight: 700;
    letter-spacing: 0.05em;
    color: rgb(255, 187, 0);
}

.cta svg {
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

.cta:hover:before {
    width: 100%;
    background: rgba(6, 117, 49, 0.664);
}

.cta:hover svg {
    transform: translateX(0);
}

.cta:active {
    transform: scale(0.95);
}
</style>