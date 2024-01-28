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
     
        <div class="wrapper">
            <div class="card">
                <div class="poster">
                    <img :src="getImages(imgPath)" alt="">
                </div>

                <div class="details">
                    <h1>{{ titleOrName }}</h1>
                    <h2>{{ originalTitleOrName }}</h2>
                    
                    <div class="rating">
                        <i v-for="i in getStarsVote" :key="i" class="fa-solid fa-star"></i>
                        <i v-for="y in (5 - getStarsVote)" :key="y" class="fa-regular fa-star"></i>
                    </div>

                    <div class="languages">
                        <img :src="getFlags" alt="">
                    </div>
                </div>
            </div>
        </div>
           
       

</template>

<style lang="scss" scoped>
        .wrapper {
            position: relative;
            width: 100%;
            height: 100%;
            padding: 20px;
            display: flex;
            align-content: center;
            justify-content: center;
            gap: 24px;
            flex-wrap: wrap;
        }


        .card {
            position: relative;
            width: 325px;
            height: 450px;
            background: #000;
            border-radius: 18px;
            box-shadow: 0 10px 10px rgba(0, 0, 0, .2);
            cursor: pointer;
            overflow: hidden;
        }
        

        .poster {
            position: relative;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

    
        .poster::before {
            content: '';
            position: absolute;
            bottom: -45%;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            transition: .3s;
        }
        
        .card:hover .poster::before {
            bottom: 0;
        }


        .poster img {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: .3s;
        }

        .card:hover .poster img {
            transform: scale(1.1);
        }

        .details {
            position: absolute;
            bottom: -100%;
            left: 0;
            width: 100%;
            height: auto;
            padding: 1.5em 1.5em 2em;
            background: #000a;
            backdrop-filter: blur(16px) saturate(120%);
            transition: .3s;
            color: #fff;
            z-index: 2;
        }

        .card:hover .details {
            bottom: 0;
        }

        .details h1, .details h2 {
            font-weight: 700;
        }

        .details h1 {
            font-size: 1.5em;
            margin-bottom: 5px;
        }

        .details h2 {
            font-weight: 400;
            font-size: 1em;
            margin-bottom: 10px;
            opacity: .6;
        }


        .details .rating {
            position: relative;
            margin-bottom: 15px;
            display: flex;
            gap: .25em;
        }

        .details .rating i {
            color: #e3c414;
        }

        .details .rating span {
            margin-left: 0.25em;
        }




        .languages img{
            width: 20%;
        }
</style>
