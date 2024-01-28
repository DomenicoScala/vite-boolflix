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
        <header>
           <div class="container">
                <div class="header-flex">
                    
                    
                    
                    <div class="title">
                        <h1>BOOLFLIX</h1>
                    </div>
                    
                    
                    <div class="searchInput">
                        <div class="first-men-header">
                            <div>
                                <ul>
                                    <li>
                                        <a href="#">Movies</a>
                                    </li>
                                    <li>
                                        <a href="#">Series</a>
                                    </li>
                                </ul>
                            </div>
                        
                            <div>
                                <input  v-model="store.searchText" type="text" placeholder="Cerca il tuo film o la serie tv..">
                    
                                <button @click="$emit('performSearch')">
                                    CERCA
                                </button>
                            </div>                        
                        </div>
                        
                        
                    </div>
                </div>
           </div> 
        </header>
        


</template>

<style lang="scss" scoped>
    @use '../assets/scss/partials/reset.scss' as *;
    

   
   
    header{
        height: 80px;
        background-color:black;;
    }
    
    .header-flex{
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px;
        background-color: black;




        .first-men-header ul{
            list-style: none;
        }

        .first-men-header div i{
            color: white;
            margin: 5px;
            font-size: 20px;
            cursor: pointer;
            vertical-align:-webkit-baseline-middle;
        }


       

        .first-men-header ul li{
            display: inline-block;
          
            
            & a{
                color: white;
                text-decoration: none;
                cursor: pointer;
                margin-right: 30px;
            }
        }

        .first-men-header ul li:hover{
            text-decoration: underline;
            color: white;
        }


        .first-men-header{
            display: flex;
            align-items: center;

        }


        h1{
            color: red;
            font-weight: bold;
            text-align: center;
            font-size: 30px;
            cursor: pointer;
        }

        .searchInput{
            text-align: center;
        }

        .searchInput input{
            background-color: rgb(255, 253, 253);
            border-radius: 10px;
            padding: 3px 10px;
            margin-right: 10px;
            border: none;
            max-width: 230px;
        }

        .searchInput button{
            padding:3px 10px;
            border-radius: 10px;
            color: white;
            background-color: black;
            border: 1px solid white;
        }
    }



</style>
