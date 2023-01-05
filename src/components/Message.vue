<template>
    <div class="display">
        <div class="message-container">
            <p>{{ msg }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Message',
    props: {
        msg: String
    }
}
</script>

<style scoped>
.display{
    display: flex;
    justify-content: center;
    align-items: center;
}
.message-container {
    color: #4a8b00;
    background-color: rgb(231, 231, 231);
    border: 2px solid #46d404;
    border-radius: 5px;
    padding-top: 20px !important;
    padding: 10px 15px 10px 10px;
    max-width: 400px;
    margin-bottom: 20px;
}

</style>