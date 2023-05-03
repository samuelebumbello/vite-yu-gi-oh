<script>
import { store } from '../../../data/store';

export default{
    name: 'Card',
    props:{
        name: String,
        img: Array,
        type: String,
    },
    data(){
        return {
            store
        }
    }
    
}
</script>
<template>

    <div class="dc-card">
        <img :src="img[0].image_url" :alt="name">
        <div class="text">
            <h5>{{ name }}</h5>
            <div class="text-center">{{ type }}</div>
        </div>
    </div>

</template>


<style lang="scss" scoped>
 .dc-container{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    .dc-card{
        width: calc(100% / 5);
        padding: 0 34px;
        margin-bottom: 20px;
        img{
            object-fit: cover;
            width: 100%;
        }
        .text{
            padding-bottom: 20px;
            height: 120px;
            background-color: #D48F38;
            h5{
                text-align: center;
                padding-top: 15px;
                padding-bottom: 10px;
                font-size: 20px;
                color: white;
            }
        }
    }
}
</style>