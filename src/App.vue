<script setup>
import Header from './components/Header.vue';
import List from './components/List.vue'
</script>

<template>
    <div id="document">

        <div id="area">
            
            <Header @save="saveItem" />

            <div id="list-area">
                <div v-for="item in list">
                    <List :list="item" @delete="deleteItem" />
                </div>
            </div>

        </div>
        <div id="author">
            <address>Feito por <a href="https://github.com/jrafael29" target="_blank">J. Rafael</a></address>
        </div>
    </div>

</template>

<script>

export default {

    data(){
        return {
            list: [],
            num: 0
        }
    },
    methods: {
        saveItem(value){
            this.num++
            this.list.unshift({
                id: this.num,
                text: value
            })
        },
        deleteItem(id){
            let index = this.list.findIndex( item => item.id == id )
            this.list.splice(index, 1);
        }
    },
    components: {
        List,
        Header
    }
}

</script>

<style scoped>
    @media(max-width: 450px){
        #area{
            max-width: 300px !important;
        }
    }
    #document{
        height: 100vh;
        width: 100vw;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    #area{
        max-width: 450px;
        width: 100%;
        max-height: 450px;
        height: 100%;
        display: flex;
        flex-direction: column;
        box-shadow: 0px 0px 15px #000;
        padding: 20px;
    }

    #list-area{
        padding: 10px;
        max-height: 100%;
        height: 100%;
        overflow-y: auto;
        scroll-behavior: smooth;
    }

    #list-area::-webkit-scrollbar-track{
    background-color: transparent;
    
    }
    #list-area::-webkit-scrollbar{
        width: 5px;
        background: transparent;  
    }
    #list-area::-webkit-scrollbar-thumb {
        background: #dad7d7;
        border-radius: 15px;
    }

    #author{
        padding: 10px 0;
        color: rgb(192, 192 ,192);
        opacity: .7;
    }

</style>
