<template>
    <section class="first-section-main">
        <SelectElement/>
    </section>
    <section class="second-section-main">
        <ListActors/>
    </section>
</template>

<script>
import SelectElement from './another-comp/SelectElement.vue';
import ListActors from './another-comp/ListActors.vue';
    export default {
        name: 'AppMain',

        components:{
        SelectElement,    
        ListActors,
    }
    }
    
</script>

<style lang="scss" scoped>

</style>