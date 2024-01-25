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

        <h1>MOVIES</h1>
        <div>
            <ul>
                <li v-for="(movies,i) in store.movies">
                    <div>
                        Titolo: {{ movies.title }}
                    </div>

                    <div>
                        Titolo Original : {{ movies.original_title }}
                    </div>

                    <div>
                        Lingua : {{ movies.original_language }}
                    </div>

                    <div>
                        Voto: {{ movies.vote_average }}
                    </div>
                </li>
            </ul>
        </div>
        

</template>

<style lang="scss" scoped>

</style>
