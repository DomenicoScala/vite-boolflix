<script>
    export default{
        data(){
            return{

            };
        },
        methods:{
            getImages(img){
                let linkImage = 'https://image.tmdb.org/t/p/'

                linkImage += 'original' + img;

                return linkImage
            },
            getStarsVote(voteAverage){

                const numInt = Math.floor(voteAverage / 2)
                
                return numInt
            }

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
            voteAverage: Number,
            imgPath: String
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
            {{ getStarsVote(voteAverage) }}
        </div>

        <div>
            <img :src="getImages(imgPath)" alt="">
        </div>
     </div>
       

</template>

<style lang="scss" scoped>
        img{
            width: 30%;
        }
</style>
