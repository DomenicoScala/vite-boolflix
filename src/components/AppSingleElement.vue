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
            },
            getStarsVote(){

                return Math.ceil(this.voteAverage / 2)

                
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
            <i v-for="i in getStarsVote" :key="i" class="fa-solid fa-star"></i>
            <i v-for="y in (5- getStarsVote)" :key="i" class="fa-regular fa-star"></i>
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
