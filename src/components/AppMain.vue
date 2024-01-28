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

    <section>
        <main>
            <div class="container">                
                <h1 v-if="store.movies.length > 0">Movies:</h1>                
                <div class="row gx-5 gy-3">       
                        <div class="col-3" v-for="(movies,i) in store.movies">
                            <ul>
                                <li>
                                    <AppSingleElement
                                    :titleOrName="movies.title"
                                    :originalTitleOrName="movies.original_title"
                                    :flag-language="movies.original_language"
                                    :voteAverage="movies.vote_average"
                                    :img-path="movies.poster_path"/>
                                </li>
                            </ul>
                        </div>
                </div>


                <h1 v-if="store.series.length > 0">Series:</h1>
                <div class="row gx-5 gy-3">
                    <div class="col-3" v-for="(series,i) in store.series">
                        <div>
                            <ul>
                                <li>
                                    <AppSingleElement
                                    :titleOrName="series.name"
                                    :originalTitleOrName="series.original_name"
                                    :flag-language="series.original_language"
                                    :voteAverage="series.vote_average"
                                    :imgPath="series.poster_path"/>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
                
            
            
                
            </div>
        
        </main>
    </section>
    

        

</template>

<style lang="scss" scoped>


        h1{
            color:white;
            margin-top: 20px;
            margin-bottom: 20px;
        }

        ul{
            list-style: none;
        }

        
</style>
