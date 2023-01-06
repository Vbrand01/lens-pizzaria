<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-4 align">
        <div class="card">
          <div class="circle"></div>
          <div class="circle"></div>
          <img src="../../public/img/card/marguerita.jpg" style="border-radius: 8px;" height="250px" alt="">
          <h1>Marguerita</h1>
          <p>É preparada com molho de tomate, manjericão, rodelas de tomate fresco, azeitona, queijo muçarela
            e orégano salpicado.</p>
        </div>
      </div>
      <div class="col-sm-4 align">
        <div class="card">
          <!-- <div class="circle"></div>
                    <div class="circle"></div> -->
          <img src="../../public/img/card/catupiry.jpg" style="border-radius: 8px;" height="250px" alt="">
          <h1>Frango com catupiry</h1>
          <p>A receita costuma levar basicamente queijo muçarela, frango, catupiry, sálvia e molho de tomate.
            Confesso que é uma das minhas preferidas!</p>
        </div>
      </div>
      <div class="col-sm-4 align">
        <div class="card">
          <div class="circle"></div>
          <div class="circle"></div>
          <img src="../../public/img/card/quatro.jpg" style="border-radius: 8px;" height="250px" alt="">
          <h1>Quatro queijos</h1>
          <p>Assim como o nome já diz, essa pizza é preparada com quatro queijos diferentes, como muçarela,
            gorgonzola, parmesão e catupiry, por exemplo.</p>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "CardsOne",
}
</script>

<style scoped>
.container {
  background-color: rgba(255, 0, 0, 0);
  padding: 10px;
  margin-top: -60px;
}

h1 {
  margin: 15px;
  font-size: 32px;
  font-weight: 700;
}

.align {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 60px;
}

.card {
  width: 100%;
  height: 100%;
  padding: 20px;
  transition: all 0.2s;
  position: relative;
  cursor: pointer;
  border: none;
  box-shadow: rgba(0, 0, 0, 0.685) 2px -4px 28px -11px;
  -webkit-box-shadow: rgba(0, 0, 0, 0.582) 2px -4px 28px -11px;
  -moz-box-shadow: rgba(0, 0, 0, 0.616) 2px -4px 28px -11px;
}

.card:hover {
  transform: scale(1.04) rotate(1deg);
}

.circle {
  width: 100px;
  height: 100px;
  background-image: url(../../public/img/ab3.png);
  position: absolute;
  animation: move-up6 2s ease-in infinite alternate-reverse;
}

.circle:nth-child(1) {
  top: -25px;
  left: -25px;
}

.circle:nth-child(2) {
  bottom: -25px;
  right: -25px;
  animation-name: move-down1;
}

@keyframes move-up6 {
  to {
    transform: translateY(-50px);
  }
}

@keyframes move-down1 {
  to {
    transform: translateY(20px);
  }
}

@media (max-width: 908px) {
  .card {
    width: 400px;
    height: 100%;
    padding: 20px;
    transition: all 0.2s;
    margin-top: 20px;
    position: relative;
    cursor: pointer;
    border: none;
    box-shadow: rgba(0, 0, 0, 0.685) 2px -4px 28px -11px;
    -webkit-box-shadow: rgba(0, 0, 0, 0.582) 2px -4px 28px -11px;
    -moz-box-shadow: rgba(0, 0, 0, 0.616) 2px -4px 28px -11px;
  }

  .circle:nth-child(2) {
    bottom: -25px;
    right: 0px;
    animation-name: move-down1;
  }

}
</style>