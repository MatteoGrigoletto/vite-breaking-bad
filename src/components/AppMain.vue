<template>
    <main>
        <section class="first-section-main">
            <SelectElement @filter="filtering"/>
        </section>
        <section class="second-section-main">
            <ListActors/>
        </section>
    </main>
</template>

<script>
import axios from 'axios';
import {store} from '../store';
import SelectElement from './another-comp/SelectElement.vue';
import ListActors from './another-comp/ListActors.vue';
    export default {
        name: 'AppMain',
    data(){
        return {
            store,
        }
    },
    components:{
        SelectElement,    
        ListActors,
    },
    methods:{
        filtering(){
           
            axios.get("https://www.breakingbadapi.com/api/characters",
        {
            params: {
                category:this.store.selectFilter
            }
        })
        .then((response) => {
                this.store.listActor = response.data;
            });
        }
    },
    created(){
      this.filtering();
        }
}
    
</script>

<style lang="scss" scoped>

</style>