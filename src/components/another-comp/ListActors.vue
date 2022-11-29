<template>
    <div class="container-70">
        <div>
            <p> Found {{store.listActor.length}} characters</p>
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
    }
</script>

<style lang="scss" scoped>

.container-70{
    background-color: var(--bg_main);
    padding: 30px;
    margin-top: 20px;
    border-radius: 10px;

    div{
        
        p{
            background-color: var(--black);
            color: white;
            padding: 10px;
            border-radius: 10px;
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