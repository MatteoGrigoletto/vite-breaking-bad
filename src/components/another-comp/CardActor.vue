<template>
    <div class="card">
        <div class="img-box">
            <img :src=" item.img " :alt=" item.category">
        </div>
        <div class="text-box">
            <h3>{{item.name}}</h3>
            <p>{{item.category}}</p>
            <p>{{item.status}}</p>
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
    background-color: var(--bg_body);
    height: 400px;
    margin: 5px;
    padding: 10px;
    border-radius: 10px;
    border: 4px solid var(--black);

    &:hover{
        transform: scale(1.1);
        .img-box{
            animation: border 2s linear infinite;
        }
         
    }
    .img-box{
        height: 300px;
        border: 1px solid white;

        img{
            height: 100%;
            object-fit: cover;
        }
    }
    .text-box{
        text-align: center;
        color: white;
        padding: 10px 0px;
    }
}
@keyframes border{
    0%{
        box-shadow:  3px 3px 3px 3px #e65c00;
    }
    50%{
        box-shadow:  3px 3px 3px 3px #18b201;
    }
    100%{
        box-shadow:  3px 3px 3px 3px #0456c8;
    }
}
</style>