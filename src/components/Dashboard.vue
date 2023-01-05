<template>

    <div class="container">
        <table class="table table-condensed">
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
                    <td>{{  pizza.id }}</td>
                    <td>{{ pizza.nome }}</td>
                    <td>{{ pizza.sabor }}</td>
                    <td>{{ pizza.sobremesa }}</td>
                    <td>{{ pizza.bebida }}</td>
                    <td>
                        <ul>
                            <li v-for="(opcional, index) in pizza.opcionais" :key="index">{{opcional}}</li>
                        </ul>
                    </td>
                    <td>
                    <div>
                        <select name="status" class="status" id="">
                            <option value="">Selecione</option>
                        </select>
                        <button class="delete-btn">Cancelar</button>
                    </div>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>

</template>

<script>
export default {
    name: "Dashboard",
    data(){
        return{
            pizzas: null,
            pizza_id: null,
            status: []
        }
    },
    methods: {
        async getPedidos(){
            const req = await fetch("http://localhost:3000/Pizzas");

            const data = await req.json();

            this.pizzas = data;

            console.log(this.pizzas)

            // resgatar status
        }
    },
    mounted(){
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

.table-condensed{
    overflow: auto;
    display: inline-block;
    background-color: transparent;
    border: 4px solid rgb(78, 6, 6);
    border-radius: 10px;
    padding: 10px;
    margin-bottom: 760px;
    box-shadow: rgb(78, 6, 6) -18px 13px 0px 4px;
    -webkit-box-shadow: rgb(78, 6, 6) -18px 13px 0px 4px;
    -moz-box-shadow: rgb(78, 6, 6) -18px 13px 0px 4px;
}

.table-condensed th{
    color: rgb(78, 6, 6);
    letter-spacing: 2px;
    font-weight: 800;
    text-transform: uppercase; 
}

.table-condensed tr{
    color: rgb(68, 68, 68);
    letter-spacing: 2px;
}

select {
    padding: 12px 6px;
    margin-right: 12px;
}

th, td{
    margin-left: 0px;
}

.status{
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

@media (max-width: 1190px){
    select{
        width: 100%;
    }
    .delete-btn{
        width: 100%;
    }
}

</style>