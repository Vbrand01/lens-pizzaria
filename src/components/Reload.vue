<template>
    <div class="container">
        <button class="btn-reload" @click="bto()"><img src="../../public/img/refresh.png" height="100" alt=""></button>
    </div>
</template>

<script>
    export default {
        name: "Reload",

        methods: {
            bto(){
                location.reload()
            }
        }
    }
</script>

<style scoped>
.container{
    display: flex;
    justify-content: end;
}
.btn-reload{
    background-color: transparent;
    border: none;
}
</style>