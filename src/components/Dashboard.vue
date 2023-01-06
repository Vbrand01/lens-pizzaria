<template>
    <div class="img">
    <img src="../../public/img/th.gif" alt="">
    </div>
    <div class="container">
        <Message :msg="msg" v-show="msg" />
        <table class="table table-condensed" id="tablecondensed">
            <thead>
                <tr>
                    <th class="order-id">ID</th>
                    <th>Cliente:</th>
                    <th>Sabor:</th>
                    <th>Sobremesa:</th>
                    <th>Bebidas:</th>
                    <th>Opcionais:</th>
                    <th>Ações:</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="pizza in pizzas" :key="pizza.id">
                    <td>{{ pizza.id }}</td>
                    <td>{{ pizza.nome }}</td>
                    <td>{{ pizza.sabor }}</td>
                    <td>{{ pizza.sobremesa }}</td>
                    <td>{{ pizza.bebida }}</td>
                    <td>
                        <ul>
                            <li v-for="(opcional, index) in pizza.opcionais" :key="index">{{ opcional }}</li>
                        </ul>
                    </td>
                    <td>
                        <div>
                            <select name="status" class="status" id="" @change="updatePizza($event, pizza.id)">
                                <option value="">Selecione</option>
                                <option v-for="s in status" :key="s.id" :value="s.tipo"
                                    :selected="pizza.status == s.tipo">
                                    {{ s.tipo }}
                                </option>
                            </select>
                            <button class="delete-btn" @click="deletePizza(pizza.id)">Cancelar</button>
                        </div>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>

</template>

<script>

import Message from './Message.vue';

export default {
    name: "Dashboard",
    data() {
        return {
            pizzas: null,
            pizza_id: null,
            status: [],
            msg: null
        }
    },
    components: {
        Message
    },
    methods: {

        filterTable() {
            var input, filter, table, tr, td, i, txtValue;
            input = document.getElementById("inputFilter");
            filter = input.value.toUpperCase();
            table = document.getElementById("tablecondensed");
            tr = table.getElementsByTagName("tr");

            // Loop through all table rows, and hide those who don't match the search query
            for (i = 0; i < tr.length; i++) {
                td = tr[i].getElementsByTagName("td")[0];
                if (td) {
                    txtValue = td.textContent || td.innerText;
                    if (txtValue.toUpperCase().indexOf(filter) > -1) {
                        tr[i].style.display = "";
                    } else {
                        tr[i].style.display = "none";
                    }
                }
            }
        },

        async getPedidos() {

            const req = await fetch("http://localhost:3000/Pizzas");

            const data = await req.json();

            this.pizzas = data;

            // resgatar status
            this.getStatus();
        },
        async getStatus() {
            const req = await fetch("http://localhost:3000/status");

            const data = await req.json();

            this.status = data;

        },
        async deletePizza(id) {
            const req = await fetch(`http://localhost:3000/Pizzas/${id}`, {
                method: "DELETE"
            });

            const res = await req.json();

            //msg
            this.msg = `Pedido removido com sucesso`;

            setTimeout(() => this.msg = "", 2000);

            this.getPedidos();
        },
        async updatePizza(event, id) {
            const option = event.target.value;

            const dataJson = JSON.stringify({ status: option });

            const req = await fetch(`http://localhost:3000/Pizzas/${id}`, {
                method: "PATCH",
                headers: { "Content-Type": "application/json" },
                body: dataJson
            });

            const res = await req.json()

            this.msg = `O pedido Nº${res.id} foi atualizado para ${res.id}!`;

            setTimeout(() => this.msg = "", 2000);

            console.log(res);
        }

    },
    mounted() {
        this.getPedidos();
    }
}
</script>

<style scoped>
/* .container thead, tbody{
    display: flex;
    align-items: center;
    justify-content: center;
} */

.img{
    display: flex;
    justify-content: center;
    align-items: center;
}

.table-condensed {
    overflow: auto;
    display: inline-block;
    background-color: transparent;
    border: 4px solid rgb(78, 6, 6);
    border-radius: 10px;
    padding: 10px;
    margin-bottom: 600px;
    box-shadow: rgb(78, 6, 6) -18px 13px 0px 4px;
    -webkit-box-shadow: rgb(78, 6, 6) -18px 13px 0px 4px;
    -moz-box-shadow: rgb(78, 6, 6) -18px 13px 0px 4px;
}

.table-condensed th {
    color: rgb(78, 6, 6);
    letter-spacing: 2px;
    font-weight: 800;
    text-transform: uppercase;
}

.table-condensed tr {
    color: rgb(68, 68, 68);
    letter-spacing: 2px;
}

select {
    padding: 12px 6px;
    margin-right: 12px;
    background-color: rgb(211, 211, 211);
    border: none;
}

th,
td {
    margin-left: 0px;
}

.status {
    border-radius: 8px;
}

.delete-btn {
    background-color: rgb(250, 6, 46);
    color: #f8fc03;
    font-weight: bold;
    border: 2px solid rgb(247, 247, 247);
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;
    border-radius: 8px;
    margin-top: 10px;
}

.delete-btn:hover {
    background: transparent;
    color: rgb(250, 6, 46);
    border: 2px solid rgb(250, 6, 46);
}

@media (max-width: 1190px) {
    select {
        width: 100%;
    }

    .delete-btn {
        width: 100%;
    }

    .container {
        margin-left: 11px;
        padding: 30px !important;
    }
}
</style>