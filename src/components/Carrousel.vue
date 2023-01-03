<template>
    <div class="fundo">
        <div class="container">
            <div class="carrousel">
                <!-- <h2>Pizzas mais deliciosas da região</h2> -->
                <splide :options="options">
                    <splide-slide>
                        <img src="../../public/img/card/p1.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                    <splide-slide>
                        <img src="../../public/img/card/p2.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                    <splide-slide>
                        <img src="../../public/img/card/p3.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                    <splide-slide>
                        <img src="../../public/img/card/p4.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                    <splide-slide>
                        <img src="../../public/img/card/p5.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                    <splide-slide>
                        <img src="../../public/img/card/p6.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                    <splide-slide>
                        <img src="../../public/img/card/p7.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                    <splide-slide>
                        <img src="../../public/img/card/p8.jpg" style="border-radius: 8px;" alt="">
                    </splide-slide>
                </splide>
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

.fundo{
    background-color: rgb(221, 221, 221);
    padding: 10px;
    margin-top: 50px;
    border-radius: 20px;
}

.carrousel {
    padding: 20px;
    border-radius: 8px;
    margin-top: 50px;
    margin-bottom: 50px;
    box-shadow: rgba(0, 0, 0, 0.685) 2px -4px 28px -11px;
    -webkit-box-shadow: rgba(0, 0, 0, 0.582) 2px -4px 28px -11px;
    -moz-box-shadow: rgba(0, 0, 0, 0.616) 2px -4px 28px -11px;
}

h2 {
    text-align: center;
    margin-top: 15px;
    color: rgb(255, 187, 0);
    font-weight: 800;
}
</style>