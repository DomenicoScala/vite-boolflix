<script>
    import AppSingleElement from './AppSingleElement.vue';
    import { store } from '../store'
    export default{
        data(){
            return{
                store
            };
        },
        methods:{
            
        },
        components:{
            AppSingleElement
        }
    }
</script>

<template>

        <h1>MOVIES</h1>
        <div>
            <ul>
                <li v-for="(movies,i) in store.movies">
                    <AppSingleElement
                    :titleOrName="movies.title"
                    :originalTitleOrName="movies.original_title"
                    :flag-language="movies.original_language"
                    :voteAverage="movies.vote_average"/>
                </li>
            </ul>
        </div>
        
        <h1>SERIES</h1>
        <div>
            <ul>
                <li v-for="(series,i) in store.series">
                    <AppSingleElement
                    :titleOrName="series.name"
                    :originalTitleOrName="series.original_name"
                    :flag-language="series.original_language"
                    :voteAverage="series.vote_average"/>
                </li>
            </ul>
        </div>

</template>

<style lang="scss" scoped>
        img{
            height: 30px;
        }
</style>
