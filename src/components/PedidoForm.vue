<template>
    <div class="container" id="pedidosHome">
        <Message :msg="msg" v-show="msg" />
        <div class="form-pizza">
            <form method="POST" @submit="createPedido">
                <div class="row">
                    <div class="col-sm-3">
                    </div>
                    <div class="col-sm-12 styleForm">
                        <div class="row">
                            <div class="col-sm-12 p-1">
                                <label for="nome">Nome do cliente:</label>
                                <input type="text" class="form-control" id="nome" name="nome" v-model="nome"
                                    placeholder="Insira o nome">
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 p-1">
                                <label for="sabor">Escolha o sabor:</label>
                                <select name="sabor" class="form-select" id="sabor" v-model="sabor">
                                    <option value="">Selecione o sabor que deseja</option>
                                    <option v-for="sabor in sabores" :key="sabor.id" :value="sabor.tipo">{{ sabor.tipo }}
                                    </option>
                                </select>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 p-1">
                                <label for="sobremesa">Escolha uma sobremesa:</label>
                                <select name="sobremesa" class="form-select" id="sobremesa" v-model="sobremesa">
                                    <option value="">Selecione a sobremesa que deseja</option>
                                    <option v-for="sobremesa in sobremesas" :key="sobremesa.id" :value="sobremesa.tipo">
                                        {{ sobremesa.tipo }}</option>
                                </select>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 p-1">
                                <label for="bebida">Escolha uma bebida:</label>
                                <select name="bebida" class="form-select" id="bebida" v-model="bebida">
                                    <option value="">Selecione a bebida que deseja</option>
                                    <option v-for="bebida in bebidas" :key="bebida.id" :value="bebida.tipo">
                                        {{ bebida.tipo }}
                                    </option>
                                </select>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 p-1" style="display:">
                                <div class="col-sm-12 p-1 m-1" style="display:">
                                    <label for="opcional">Borda:</label>
                                    <div class="content" v-for="opcional in opcionaisdata" :key="opcional.id"
                                        value="opcional.tipo">
                                        <input type="checkbox" class="form-check-input" name="opcionais" id="opcional" v-model="opcionais"
                                            :value="opcional.tipo">
                                        <span>{{ opcional.tipo }}</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-sm-12 p-1 mt-2">
                                <input type="submit" id="submit" value="Enviar pedido"
                                    class="btn btn-outline-success w-100 submit">
                            </div>
                            <div class="col-sm-3"></div>
                        </div>
                    </div>
                </div>
            </form>

        </div>
    </div>
</template>

<script>

import Message from './Message.vue';

export default {
    name: 'PedidoForm',

    data() {
        return {
            sabores: null,
            sobremesas: null,
            bebidas: null,
            opcionaisdata: null,
            nome: null,
            sabor: null,
            sobremesa: null,
            bebida: null,
            opcionais: [],
            msg: null
        }
    },
    methods: {
        async getIngredientes() {

            const req = await fetch("http://localhost:3000/ingredientes");
            const data = await req.json();

            this.sabores = data.sabores;
            this.sobremesas = data.sobremesas;
            this.bebidas = data.bebidas;
            this.opcionaisdata = data.opcionais;
        },
        async createPedido(e) {
            e.preventDefault()

            const data = {
                nome: this.nome,
                sabor: this.sabor,
                sobremesa: this.sobremesa,
                bebida: this.bebida,
                opcionais: Array.from(this.opcionais),
                status: "Solicitado"
            }

            const dataJson = JSON.stringify(data);

            const req = await fetch("http://localhost:3000/Pizzas", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });

            const res = await req.json();

            // colocar uma msg de sistema
            this.msg = `Pedido Nº ${res.id} realizado com sucesso`;

            setTimeout(() => this.msg = "", 2000);

            // limpar os campos
            this.nome = "";
            this.sabor = "";
            this.sobremesa = "";
            this.bebida = "";
            this.opcionais = [];


        },
        
    },

    mounted() {
        this.getIngredientes()
    },

    components: {
        Message
    }

}
</script>

<style scoped>
.container {
    padding: 20px;
}

.styleForm {
    background-color: rgba(48, 4, 4, 0.945);
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.137);
    backdrop-filter: blur(7.9px);
    -webkit-backdrop-filter: blur(7.9px);
    padding: 40px;
    border-radius: 20px;
    transition: 0.8s;
    -webkit-box-shadow: 2px 6px 22px 1px rgba(0,0,0,0.75);
    -moz-box-shadow: 2px 6px 22px 1px rgba(0,0,0,0.75);
    box-shadow: 2px 6px 22px 1px rgba(247, 3, 3, 0.75);

}

.styleForm:hover{
    border: 3px solid rgba(255, 255, 0, 0.973);
}

input,
select {
    border: none;
    background-color: rgb(77, 18, 18);
    color: rgb(204, 204, 204);
}


label {
    color: rgb(228, 175, 0);
    font-weight: 700;
    letter-spacing: 1px;
    font-size: 19px;
}

span {
    color: rgb(189, 189, 189);
    font-weight: 600;
    margin-left: 5px;
    letter-spacing: 2px;
    font-size: 15px;
}

.sub {
    font-size: 15px;
    color: rgb(156, 156, 156);
}

.submit {
    color: white;
    background-color: rgb(250, 6, 46);
    transition: 0.4s;
}

.submit:hover {
    color: rgb(255, 187, 0);
    background-color: rgb(250, 6, 46);
    font-size: 28px;
    border-radius: 100px;
    font-weight: 800;
    letter-spacing: 2px;
}


@media (max-width: 768px) {
    .container {
        padding: 25px !important;
    }

    .form-pizza {
        border-radius: 20px;
    }
}

@media (max-width: 900px) {
    .styleForm {
        width: 100%;
    }
}

.clear {
    clear: both;
}

.checkBox {
    display: block;
    cursor: pointer;
    width: 30px;
    height: 30px;
    border: 3px solid rgba(255, 255, 255, 0);
    border-radius: 10px;
    position: relative;
    overflow: hidden;
    box-shadow: 0px 0px 0px 2px #fff;
}

.checkBox div {
    width: 60px;
    height: 60px;
    background-color: rgb(255, 187, 0);
    top: -52px;
    left: -52px;
    position: absolute;
    transform: rotateZ(45deg);
    z-index: 100;
}

.checkBox input[type=checkbox]:checked+div {
    left: -10px;
    top: -10px;
}

.checkBox input[type=checkbox] {
    position: absolute;
    left: 50px;
    visibility: hidden;
}

.transition {
    transition: 300ms ease;
}
</style>