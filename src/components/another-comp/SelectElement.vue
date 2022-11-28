<template>
    <div class="container-70">
        <form>
            <label for="category"></label>
            <select name="category" id="category">
                <option value="#">Select category</option>
                <option value="#">#</option>
                <option value="#">#</option>
                <option value="#">#</option>
            </select>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'SelectElement',
    }
</script>

<style lang="scss" scoped>
.container-70{
   margin-top: 30px;
   
   form{

        select{
            padding: 10px 20px;
            border-radius: 10px;
            background-color: antiquewhite;

            option{
                color: greenyellow;
                background-color: grey;
            }
        }
   }

}
</style>