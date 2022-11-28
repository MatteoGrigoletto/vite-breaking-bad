<template>
    <div class="card">
        <div>
            <img src="" alt="">
        </div>
        <div>
            <h3>{{item.name}}</h3>
            <p>{{}}</p>
            <p>Alive</p>
        </div>
    </div>
</template>

<script>
    export default {
        name:'CardActor',
        props:{
            item:Object,
        }
    }
</script>

<style lang="scss" scoped>

.card{
    width: calc(100% / 5 - 10px);
    background-color: aqua;
}
</style>