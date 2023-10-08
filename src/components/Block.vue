<template>
    <div class="block">
        <img v-if="power === 1 || power === 2" src="../assets/power_1.png">
        <img v-else-if="power === 3 || power === 4" src="../assets/power_2.png">
        <img v-else-if="power === 5 || power === 6" src="../assets/power_3.png">
        <img v-else-if="power === 7 || power === 8" src="../assets/power_4.png">
        <img v-else-if="power === 0" src="../assets/power_0.png">
        <p>Processor: {{ cpu }}</p><br>
        <p>Graphics: {{ gpu }}</p><br>
        <p>RAM: {{ ram }}</p><br>
        <p>Storage: {{ storage }}</p><br>
        <p>Power Rating: {{ power }}</p>
    </div>
</template>

<script>
export default {
    name: 'PCBlock',
    data(){
      return{
        
      }
    },
    methods:{
      
    },
    props:['cpu','gpu','ram','storage','power']
  }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css?family=Kalam');

    html,body
    {
        padding:0;
        margin:0;
    }

    p
    {
        margin:-1vh 0;
        line-height: 5vh;
        font-size:calc(1.5vh + 1.5vw);
        font-family: Kalam;
        color:#190019;
        font-weight:600;
    }

    img
    {
        width:80%;
        height:33%;
    }

    .block
    {
        height:auto;
        width:19.5vw;
        border:3px solid #DFB6B2;
        padding:2vh 1.5vw;
        background: transparent;
        position:relative;
        margin:20vh 1vw;
        display:inline-block;
        border-radius:18px;
    }

    @media screen and (max-width:1298px)
    {
        p
        {
            line-height: 3vh;
            font-size:calc(1vh + 1vw);
        }

        .block
        {
            border:2.5px solid #DFB6B2;
            padding:1.5vh 1vw;
            margin:24vh 1vw;
        }
    }

    @media screen and (max-width:900px)
    {
        p
        {
            font-size:calc(0.75vh + 0.75vw);
        }

        .block
        {
            width:16vw;
        }
    }

    @media screen and (max-width:700px)
    {
        .block
        {
            border:3px solid #DFB6B2;
            width:33.33vw;
            margin:2vh 3vw;
            padding:2vh 2vw;
            font-weight:400;
        }

        p
        {
            font-size:calc(1.4vh + 1.4vw);
            line-height:4vh;
            font-weight:600;
        }
    }
</style>