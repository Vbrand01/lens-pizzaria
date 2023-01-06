<template>
    <div class="fundo">
        <div class="container">
            <div class="row">
                <div class="col-xl-4 display">
                    <p
                        style="text-align: center; color: blue; background-color: white; border-radius: 800px 100px; padding: 15px;">
                        <img src="https://img.icons8.com/ios-glyphs/70/null/increase-discount.png" />
                    </p>
                    <h3>Desconto</h3>
                    <p>30% de desconto (Primeira compra)</p>
                </div>
                <div class="col-xl-4 display">
                    <p
                        style="text-align: center; color: blue; background-color: white; border-radius: 800px 800px 100px 150px; padding: 15px;">
                        <img src="https://img.icons8.com/ios/70/red/--pocket-watch.png" />
                    </p>
                    <h3>Horários</h3>
                    <p>16h00 até 00h30</p>
                </div>
                <div class="col-xl-4 display">
                    <p
                        style="text-align: center; color: blue; background-color: white; border-radius: 100px 800px; padding: 15px;">
                        <img src="https://img.icons8.com/sf-regular/70/null/motorcycle.png" />
                    </p>
                    <h3>Frete</h3>
                    <p>Apenas R$2,99</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "Faixa"
}

</script>

<style scoped>
.fundo {
    background-color: rgb(77, 18, 18);
    margin-top: 50px;
    height: 200px;
    padding: 40px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.display {
    padding: 0px;
    border-radius: 8px;
    padding-bottom: 20px;
}

h3,
p {
    text-align: center;
}

h3 {
    color: rgb(228, 175, 0);
}

p {
    color: rgb(219, 219, 219);
}

@media (max-width: 1200px) {
    .fundo {
        height: 800px;
    }
}
</style>