<template>
    <div class="container-70">
        <form @change="$emit('filter')">
            <label for="category"></label>
            <select name="category" id="category" v-model="store.selectFilter">
                <option value="">Select category</option>
                <option value="Better Call Saul">Better Call Sauk</option>
                <option value="Breaking Bad">Breaking Bad</option>
            </select>
        </form>
    </div>
</template>

<script>
import {store} from '../../store';
    export default {
        name: 'SelectElement',
        data(){
            return {
                store,
            }
        }
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