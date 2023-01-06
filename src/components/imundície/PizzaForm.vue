<template>
    <div>
        <p style="text-align: center;" hidden>Componente de Mensagem</p>
        <br><br><br><br>
        <div>
            <form id="pizza-form">
                <div class="input-container">
                    <label for="name">Nome do cliente:</label>
                    <input type="text" id="name" name="name" v-model="name" placeholder="Digite o seu nome">
                </div>
                <div class="input-container">
                    <label for="flavor">Escolha o sabor:</label>
                    <select id="flavor" name="flavor" v-model="flavor">
                        <option value="">Selecione a sua pizza</option>
                        <option value="calabresa">Calabresa</option>
                    </select>
                </div>
                <div id="opcionais-container" class="input-container">
                    <label id="opcionais-title" for="opcionais">Selecione os opcionais:</label>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="aaaaaa">
                        <span>Catupiry</span>
                    </div>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="aaaaaa">
                        <span>Maionese</span>
                    </div>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="aaaaaa">
                        <span>Cebola</span>
                    </div>
                </div>
                <div class="input-container">
                    <label for="dessert">Escolha uma sobremesa:</label>
                    <select id="dessert" name="dessert" v-model="flavor">
                        <option value="">Selecione uma sobremesa</option>
                        <option value="calabresa">Chocolate</option>
                    </select>
                </div>
                <div class="input-container">
                    <label for="drink">Escolha uma bebida:</label>
                    <select id="drink" name="drink" v-model="drink">
                        <option value="">Selecione uma bebida</option>
                        <option value="cocacola">Coca-cola</option>
                    </select>
                </div>

                <div class="input-container">
                    <input type="submit" class="submit-btn" value="Fazer meu pedido">
                </div>

            </form>
        </div>
    </div>
</template>

<script>
    export default {
        name: "PizzaForm"
    }
</script>

<style scoped>


#pizza-form{
    max-width: 400px;
    margin: 0 auto;
}

.input-container{
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}

label{
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #fc3503;
}

input, select {
    padding: 5px 10px;
    width: 300px;
}

#opcionais-container{
    flex-direction: row;
    flex-wrap: wrap;
}

#opcionais-title{
    width: 100%;
}

.checkbox-container{
    display: flex;
    align-items: flex-start;
    width: 50%;
    margin-bottom: 20px;
}

</style>