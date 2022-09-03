
<template>
    <div id="header-form">
        <form action="" @submit.prevent="" @keyup.enter="handleEmit">
            <input type="text" v-model="value" :placeholder="place">
        </form>
    </div>
</template>
<script>

    export default {
        data(){
            return {
                value: '',
                place: 'Escreve e pressione enter para salvar'
            }
        },
        methods: {
            handleEmit(){
                this.$emit('save', this.value)
                this.value = ''
            }
        }
    }
    
    </script>

<style scoped>
    @media(max-width: 450px){
        form input{
            font-size: 12px !important;
        }
    }
    #header-form{
        padding: 10px;
    }

    form{
        display: flex;
        gap: 5px;
    }
    form input{
        flex: 1;
        padding: 8px;
        background: transparent;
        outline: 0;
        border: 0;
        text-align: center;
        font-size: 20px;
        color: rgb(189, 189, 189);

    }

    form button{
        padding: 8px;
    }
</style>