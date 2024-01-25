<script>
    import { store } from '../store'
    export default{
        data(){
            return{
                store
            };
        },
        methods:{

        }
    }
</script>

<template>
        <div>
            <input  v-model="store.searchText" type="text" placeholder="Cerca il tuo film o la serie tv..">

            <button @click="$emit('performSearch')">
                CERCA
            </button>
        </div>
        


</template>

<style lang="scss" scoped>
 
</style>
