<template>
    <div class="container-70">
        <div class="counter">
            <p> Found {{totalActors}} characters</p>
            <p> Characters dead: {{actorStatus}}</p>
        </div>
        <div class="container-cards" v-if="active === false">

            <AppLoader @click="active = true"/>

        </div>
        <div class="container-cards" v-else>  

            <CardActor v-for="actor in store.listActor"
             :item="actor" />
        </div>
    </div>

</template>

<script>
import { store } from '../../store';

import CardActor from './CardActor.vue';
import AppLoader from './AppLoader.vue';

    export default {
        name:'ListActors',
        data(){{
            return{
                store,
                active: false,
            }
        }},
        components:{
            CardActor,
            AppLoader,
        },
        computed: {
            totalActors(){
                return store.listActor.length;
            },
            actorStatus() {

                    let dead = 0;
                    this.store.listActor.forEach(element => {
                        if(element.status == 'Deceased'){
                            dead++;
                        }
                    });
                return dead;
                }
            }
    }
</script>

<style lang="scss" scoped>

.container-70{
    background-color: var(--bg_main);
    padding: 30px;
    margin-top: 20px;
    border-radius: 10px;

    .counter{
        display: flex;
        justify-content: space-around;

        p{
            background-color: var(--black);
            color: white;
            padding: 10px;
            border-radius: 10px;
            width: 40%;
            text-align: center;
            border: 2px solid white;
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