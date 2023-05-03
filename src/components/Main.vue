<script>
import { store } from "../../data/store";
import Card from "../components/partials/Card.vue";

export default {
    name: "Main",
    components:{
        Card,
        
    },
    data(){
        return {
            store
        }
    },
}
</script>
<template>
    <div class="bg-color">
        <main>
            <div class="return fw-bold">
                <span class="found-card">Found 15 cards</span>
            </div>
            <div class="dc-container">
                <Card
                v-for="card in store.resultArray"
                :key="card.id"
                :img="card.card_images"
                :name="card.name"
                :type="card.type"
                />
            </div>
        </main>
    </div>
</template>


<style lang="scss" scoped>
    .bg-color{
        background-color: #D48F38;
        padding-top: 100px;
    }
    main{
        margin: 0 auto;
        background-color: white;
        padding-top: 32px;
        width: 70%;
        .return{
            display: flex;
            align-items: center;
            margin: 0 auto;    
            width: 95%;
            height: 55px;
            background-color: #212529;
            color: white;
            padding-left: 15px;
        }
        .dc-container{
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }
    }
</style>