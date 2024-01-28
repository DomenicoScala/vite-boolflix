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
     
    <div class="card-film">
        <!-- <div class="poster">
            <img :src="getImages(imgPath)" alt="">
        </div> -->
        <div class="details">
            <h1>{{ titleOrName }}</h1>
            <h2>{{ originalTitleOrName }}</h2>

            <div class="rating">
                <i v-for="i in getStarsVote" :key="i" class="fa-solid fa-star"></i>
                <i v-for="y in (5- getStarsVote)" :key="y" class="fa-regular fa-star"></i>
            </div>

            <div class="lang">
                <img :src="getFlags" alt="">
            </div>

        </div>
        
        
    </div>
       

</template>

<style lang="scss" scoped>
        .card-film{
            width: 300px;
            height: 425px;
            background: #000;
            border-radius: 18px;
            overflow: hidden;
            box-shadow: 0 10px 10px rgba(0, 0, 0, .2);
            cursor: pointer;
        }

        .poster{
            width: 100%;
            height: 100%;
            overflow: hidden;
            position: relative;          
        }

        .poster img{
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: .3s;
        }


        
        

        

    

        

        .lang img{
            width: 20%;
        }
</style>
