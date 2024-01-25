<script>
    import AppHeader from './components/AppHeader.vue'
    import AppMain from './components/AppMain.vue'
    import AppFooter from './components/AppFooter.vue'
    import axios from 'axios'
    import { store } from './store'    
    export default{
        data(){
            return{
                store
            };
        },
        methods:{
            searchMoviesAndSeries(){
                axios
                .get('https://api.themoviedb.org/3/search/movie',{
                params:{
                    api_key: '75f999b36477ad9440a83dba9f6ac3ad',
                    query: this.store.searchText
                }
                })
                .then((response) =>{
                console.log(response.data.results)
                this.store.movies = response.data.results
                this.store.searchText = ''

                })
            }
           

        },
        components:{
            AppHeader,
            AppMain,
            AppFooter
        },
        mounted(){  
           
        }
    }
</script>

<template>

        <AppHeader @performSearch="searchMoviesAndSeries()"/>

        <AppMain/>

        <AppFooter/>

</template>

<style lang="scss">
    @use "assets/scss/main.scss" as *;
    @use "assets/scss/partials/reset.scss" as *;
</style>
