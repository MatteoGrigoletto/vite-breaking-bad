<template>
    <div class="container-70">
        <div>
            <p> Found {{listActor.length}} characters</p>
        </div>
        <div class="container-cards" v-if="active === false || listActor.length < 62">
            <AppLoader @click="active = true"/>
        </div>
        <div class="container-cards" v-else>  

            <CardActor v-for="actor in listActor"
             :item="actor" />
        </div>
    </div>

</template>

<script>
import axios from 'axios';
import CardActor from './CardActor.vue';
import AppLoader from './AppLoader.vue';

    export default {
        name:'ListActors',
        data(){{
            return{
                listActor: [],
                active: false,
            }
        }},
        components:{
            CardActor,
            AppLoader,
        },
        created(){
            axios.get("https://www.breakingbadapi.com/api/characters").then((response) => {
                this.listActor = response.data;
                console.log(this.listActor)
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