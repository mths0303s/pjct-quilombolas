<template>
    <div class="homeComp m-0 p-0">
      <div class="text-home">
          <div class="title" data-aos="fade-left" data-aos-duration="1500">
              <h2>Quilombolas</h2>
          </div>
          <div class="sub-title">
              <h3>Povos Originários</h3>
              <h3>do <span class="brasil">Brasil</span></h3>
          </div>
          <div class="text">
              <p>Entre na jornada onde adentramos nas suas origens, localizações principais, suas produções, e mais importante, sua cultura....</p>
          </div>
          <button class="down-button btn" @click="scrollBehavior">
            <p class="m-0">Saiba Mais</p>
            <i class="material-symbols-outlined">expand_more</i>
          </button>
      </div>
      <div class="img-home">
          <img src="../../assets/mulher-quilombola.svg" alt="Mulher Quilombola">
      </div>
      
      <div class="circulos">
          <div class="circulo2">
              <svg xmlns="http://www.w3.org/2000/svg" width="147" height="147" viewBox="0 0 147 147" fill="none">
                  <circle cx="73.5" cy="73.5" r="73.5" fill="#4A2F2F"/>
              </svg>
          </div>
          <div class="circulo1">
      
          </div>
          <div class="circulo3">
              <svg xmlns="http://www.w3.org/2000/svg" width="250" height="250" viewBox="0 0 147 147" fill="none">
                  <circle cx="73.5" cy="73.5" r="73.5" fill="#4A2F2F"/>
              </svg> 
          </div>
      </div>
    </div>
</template>
  
<script>
  
  export default {
    name: 'HomeComponent',
    methods: {
        scrollBehavior() {
            window.scroll({top: window.innerHeight, behavior: "smooth"})
        }
    }
  }
</script>
  
<style scoped lang="less">
  
.homeComp{
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    height: 100vh;
    width: 100%;
    justify-content: space-around;
    margin: 0;
    padding: 0;
    overflow: hidden;
}

.text-home{
    width: 60%;
    height: 70vh;
    display: inline;
    z-index: 1;

    .title{
        
        h2{

            color: #000;

            margin-bottom: 2vh;
            font-size: calc(5em + 1vw);
            opacity: 0.8;
        }
    }

    .sub-title{
        margin-bottom: 20px;
        h3{

            color: #000;
            font-size: 2em;
        }

        .brasil {
            color: rgb(92, 35, 35);
        }
    }

    .text{
        width: 60%;
        margin-bottom:20px;
        p {

            color: #000;
            font-size: 28px;
        }
    
    }

    a{
        text-decoration: none;
    }

    .down-button{
        background-color: transparent;
        z-index: 100;

        display: flex;
        align-items: center;
        justify-content: center;
        width: fit-content;

        padding: 10px;
        border-radius: 30px;
        border: 1px solid #000000;
        box-shadow: 1px 1px 10px 1px #000;
        transition: all .5s linear;

        overflow: hidden;
        cursor: pointer;
        i{  
            color: #000;
            
            animation: moveUpDownArrow;
            animation-duration: 2s;
            animation-iteration-count: infinite;
        }

        p{
            color: #000;
        }
    }

    .down-button:hover{
        background-color: #4A2F2F;
    }
    
    .down-button:active{
        background-color: #6d4a4a;
        transform: scale(0.9);
    }
}

.img-home{
    display: flex;
    align-items: flex-end;
    z-index: 0;
    img{
        width: 75vh;
        height: auto;
        position: absolute;
        bottom: 0px;
        right: 0px;
    }
}

.circulos
{   
    z-index: -1;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    overflow-y: hidden;
    overflow-x: hidden;
}
.circulo1
{
    z-index: -1;

    position: absolute;
    left: 50%;
    right: 0;
    width: 60vh;
    height: 60vh;
    border-radius: 50%;
    background: #4A2F2F;
    animation: moveUpDown 4s ease-in-out infinite;

}
.circulo2
{
    z-index: -1;

    position: absolute;
    left: 40%;
    top: 60%;
    animation: moveUpDown 2.5s ease-in-out infinite;
}
.circulo3
{
    z-index: -1;

    position: absolute;
    left: 0;
    bottom: 0;
    animation: moveUpDown 2.5s ease-in-out infinite;
}

@keyframes moveUpDown {
    0%, 100% {
      transform: translateY(0); /* Inicial e estado final: sem deslocamento vertical */
    }
    50% {
      transform: translateY(-1.25rem); /* Estado intermediário: desloca 20px para cima */
    }
}
@keyframes moveUpDownArrow {
    0%, 100% {
      transform: translateY(0.1rem); /* Inicial e estado final: sem deslocamento vertical */
    }
    50% {
      transform: translateY(-0.2rem); /* Estado intermediário: desloca 20px para cima */
    }
}

.dark{
    .img-home{
        img{
            opacity: 0.9;
        }
    }
    .title{
        
        h2{

            color: #ffffff;
        }
    }

    .sub-title{
        h3{
            
            color: #ffffff;
        }
        .brasil {
            color: rgb(116, 64, 64);
        }
    }

    .text{
        p{
            color: #ffffff;
        }
    }

    .down-button{
        border: 1px solid #ffffff;
        
        i{  
            color: #ffffff;
        }

        p{
            color: #ffffff;
        }
    }

    @media screen and (max-width: 600px){
        .circulo1{
            opacity: .5;
        }
        .circulo3{
            opacity: .5;
        }
    }
}
@media screen and (max-width: 1000px){
    .homeComp {
        height: calc(var(--vh, 1vh) * 100);
    }

}
@media screen and (max-width: 1025px){


    .img-home{
        img{
            width: 50vh;
        }
    }

    .text-home{
        height: 85vh;

        .title{
            margin: 20px 0;
            h2{
                font-size: calc(3em + 2vw);
            }
        }

        .sub-title{
            h3{
                font-size: 1.5em;
            }
        }

        .text{
            width: 70%;
            p{
                font-size: 25px;
            }
        }
    }

    .down-button{
        i{  
            font-size: 20px;
        }
        
        p{
            font-size: 15px;
        }
    }
}    

@media screen and (max-width: 600px){

    .homeComp{
        justify-content: start;
    }

    .img-home{
        position: absolute;
        right: 0;
        bottom: 0;
        overflow: hidden;
        img{
            width: 50vh;
            position: relative;
            left: 10%;
        }
    }

    
    .text-home{
        height: 80vh;
        margin-left: 10px;
        justify-content: start;
        .title{
            h2{
                text-align: center;
                font-size: calc(3em + 2vw);
            }
        }

        .sub-title{
            h3{
                font-size: 1.5em;
            }
        }
        .text{
            width: 80%;
            p{
                font-size: 18px;
            }
        }
    }

    .circulo1{
        opacity: .8;
    }
    .circulo3{
        opacity: .8;
    }
    .circulo2{
        display: none;
    }

    .down-button{
        i{  
            font-size: 18px;
        }
        
        p{
            font-size: 12px;
        }
    }
}    
@media screen and (max-width: 300px){

    .homeComp{
        justify-content: start;
    }

    
    .text-home{
        .title{
            margin: 10px 0;
            h2{
                text-align: center;
                font-size: calc(2em + 2vw);
            }
        }

        .sub-title{
            margin-bottom: 10px;
            h3{
                font-size: 1em;
            }
        }

        .text{
            width: 70%;
            p{
                font-size: 15px;
            }
        }
    }

    .down-button{
        i{  
            font-size: 15px;
        }
        
        p{
            font-size: 10px;
        }
    }
}    
  
  </style>