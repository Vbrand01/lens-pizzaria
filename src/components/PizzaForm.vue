<template>
    <div>
        <p>Componente de Mensagem</p>
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
                <div class="input-container">
                    <label for="opcionais">Selecione os opcionais:</label>
                    <div class="checkbox-container">
                        <input type="checkbox" name="opcionais" v-model="opcionais" value="aaaaaa">
                        <span>Catupiry</span>
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
                    <select id="drink" name="drink" v-model="flavor">
                        <option value="">Selecione uma bebida</option>
                        <option value="calabresa">Coca-cola</option>
                    </select>
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

</style>