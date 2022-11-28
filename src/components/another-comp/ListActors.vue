<template>
    <div class="container-70">
        <div>
            <p> Found {{listActor.length}} characters</p>
        </div>
        <div class="container-cards">
            <CardActor v-for="actor in listActor"
             :item="actor" />
        </div>
    </div>

</template>

<script>
import axios from 'axios';
import CardActor from './CardActor.vue';
    export default {
        name:'ListActors',
        data(){{
            return{
                listActor: [],
            }
        }},
        components:{
            CardActor,
        },
        created(){
            axios.get("https://www.breakingbadapi.com/api/characters").then((response) => {
                this.listActor = response.data;
            });
        }
    }
</script>

<style lang="scss" scoped>

.container-70{
    background-color: var(--bg_main);
    padding: 30px;
    margin-top: 20px;

    div{
        
        p{
            background-color: var(--black);
            color: white;
            padding: 10px;
        }
    }
    .container-cards{
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        margin-top: 30px;

    }
}

</style>