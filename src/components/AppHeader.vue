<template>
<header>
    <section class="first-section-header">
        <div>
            <img src="../assets/br.png" alt="beakingB Bad">
        </div>
        <div>
            <h1>Breaking Bad Api</h1>
        </div>
    </section>
</header>
</template>


<script>
    export default {
        name:'AppHeader',
    }
</script>

<style lang="scss" scoped>

.first-section-header{
    display: flex;
    color: white;

    div{
        padding: 10px;
        font-size: 30px;
        img{
        width: 80px;
        }
    }
}

</style>