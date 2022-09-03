<template>

    <div class="list-item" :id="list.id">
        <div class="item">
            {{list.text}}
        </div>
        <div class="button-area">
            <button class="button" @click.prevent="$emit('delete', list.id)" >
                <i class="fas fa-trash"></i>
            </button>
        </div>
    </div>

</template>
Lorem ipsum dolor sit amet consectetur, adipisicing elit. Sed unde amet, repellendus exercitationem illum voluptatum suscipit soluta! Dolor vel ab, cum deserunt nobis aut totam illum maiores officia accusantium odit.
<script>
    export default {
        props: {
            list: Object
        },
        data(){
            return {
                
            }
        }
    }
</script>

<style scoped>
    @media(max-width: 450px){
        .list-item{
            font-size: 14px !important;
        }
    }
    .list-item{
        font-size: 20px;
        padding: 15px 10px;
        margin-bottom: 8px;
        box-shadow: 0px 0px 8px #000;
        color: rgb(189, 189, 189);
        display: flex;
        justify-content: space-between;
    }

    .list-item{
        max-width: 100%;
        word-break: break-all;
        flex: 1;
        text-align: justify;
        word-break: keep-all;
    }
    .button-area{
        min-width: 50px;
        max-width: 50px;
        width: 100%;
    }
    .button{
        width: 100%;
        background: transparent;
        border: none;
        cursor: pointer;
    }

    .button:hover{
        opacity: .5;
    }

</style>