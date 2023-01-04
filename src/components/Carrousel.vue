<template>
    <div class="fundo">
        <div class="container">
            <div class="row">
                <div class="col-sm-6">
                    <div class="carrousel">
                        <!-- <h2>Pizzas mais deliciosas da região</h2> -->
                        <splide :options="options">
                            <splide-slide>
                                <img src="../../public/img/card/p1.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p2.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p3.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p4.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p5.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p6.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p7.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p8.jpg" alt="">
                            </splide-slide>
                        </splide>
                    </div>
                </div>

                <div class="col-sm-6 mobile">
                    <div class="carrousel">
                        <!-- <h2>Pizzas mais deliciosas da região</h2> -->
                        <splide :options="options">
                            <splide-slide>
                                <img src="../../public/img/card/p4.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p5.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p6.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p7.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p8.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p1.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p2.jpg" alt="">
                            </splide-slide>
                            <splide-slide>
                                <img src="../../public/img/card/p3.jpg" alt="">
                            </splide-slide>
                        </splide>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>

import { Splide, SplideSlide } from '@splidejs/vue-splide';
import { Grid } from '@splidejs/splide-extension-grid';
import { removeDotSegments } from 'uri-js';


export default {
    components: {
        Splide,
        SplideSlide,
        Grid,
    },
    data() {
        return {
            options: {
                autoScroll: {
                    speed: 1,
                },
                cover: true,
                heightRatio: 0.5,
                // width : '100vw',
                // height: '100vh',
                // type   : 'loop',
                perPage: 1,
                focus: 'center',
                direction: 'ttb',
                wheel: true,
            },

        };
    },
}


</script>

<style scoped>
.fundo {
    background-image: url('../../public/img/pizzahome3.png');
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
    padding: 20px;
    margin-top: 50px;
    border-radius: 20px;
}

.carrousel {
    color: rgb(221, 221, 221);
    text-align: center;
    background: rgba(53, 4, 2, 0.5);
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(7.9px);
    -webkit-backdrop-filter: blur(7.9px);
    padding: 40px;
    border-radius: 10px;
    height: 100%;
    gap: 20px;
}

h2 {
    text-align: center;
    margin-top: 15px;
    color: rgb(255, 187, 0);
    font-weight: 800;
}

.splide__slide {
    border-radius: 50px !important;
}

@media (max-width: 575px){
    .col-sm-6{
        padding: 10px !important;
    }
}
</style>