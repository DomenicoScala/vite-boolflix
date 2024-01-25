<script>
    export default{
        data(){
            return{

            };
        },
        methods:{

        },
        computed:{
            getFlags(){
                let finalLink = 'https://flagicons.lipis.dev/flags/4x3/'
                if(this.flagLanguage == 'en'){
                    finalLink += 'gb'
                }
                else if(this.flagLanguage == 'ja'){
                    finalLink += 'jp'
                }
                else{
                    finalLink += this.flagLanguage
                }

                finalLink += '.svg'

                return finalLink
            }
        },
        props:{
            titleOrName: String,
            originalTitleOrName: String,
            flagLanguage: String,
            voteAverage: Number
        }
    }
</script>

<template>
     
     <div>
        <div>
            {{ titleOrName }}
        </div>

        <div>
            {{ originalTitleOrName }}
        </div>

        <div>
            <img :src="getFlags" alt="">
        </div>

        <div>
            {{ voteAverage }}
        </div>
     </div>
       

</template>

<style lang="scss" scoped>
        img{
            height: 50px;
        }
</style>
