<template>
    <div class="wrapper">
        <Block cpu="?????" gpu="?????" ram="?????" storage="?????" :power="matchme"/>
        <div class="scoreboard">
            <p class="score">Score:{{ score }}</p>
            <p class="score" style="margin-top:-3.33vh;">Rank:
                <span style="color:#a260c0;" v-show="score < 100">Starter</span>
                <span style="color:#d8976b;" v-show="score < 250 && score >= 100">Basic</span>
                <span style="color:#cfc563;" v-show="score < 500 && score >= 250">Average</span>
                <span style="color:#76c060;" v-show="score < 1000 && score >= 500">Above average</span>
                <span style="color:#60c0ab;" v-show="score < 2000 && score >= 1000">Enthusiast</span>
                <span style="color:#606ac0;" v-show="score >= 2000">Expert</span>
            </p>
            <button class="next" @click="gotoNext">Next</button>
            <p class="praise">{{praise}}</p>
        </div>
        <Block v-bind:cpu="computer.processor" v-bind:gpu="computer.gpu" 
               v-bind:ram="computer.ram" v-bind:storage="computer.storage" v-bind:power="computer.power"/>
    </div>
</template>

<script>
import Block from './Block.vue'
export default {
    name: 'MainDiv',
    components:{
        Block,
    },
    data(){
      return{
      }
    },
    methods:{
      gotoNext()
      {
        this.nextPC()
      }
    },
    props:{
    computer:Object,
    matchme:Number,
    nextPC:Function,
    score:Number,
    praise:String
    }
  }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Architects+Daughter');
    html,body
    {
        padding:0;
        margin:0;
    }

    .wrapper
    {
        height:100vh;
        width:67.333vw;
        position:absolute;
        right:0;
        top:0;
        border-radius:18px;
        background-color: #AFE4F5;
        overflow:none;
        text-align: center;
        align-items: center;
        justify-content: space-evenly;
    }

    .scoreboard
    {
        width:15vw;
        height:30vh;
        display:inline-block;
        position:relative;
        margin:27.5vh 1vw;
    }

    .score
    {
        font-size:calc(1.5vh + 1.5vw);
        font-family:Architects Daughter;
        font-weight:bold;
    }

    .praise
    {
        font-size:calc(1vh + 1vw);
        font-family:Architects Daughter;
        font-weight:bold;
    }

    .next
    {
        background: transparent;
        border:none;
        font-family:Architects Daughter;
        margin:0;
        font-weight:bold;
        border:1px solid black;
    }

    @media screen and (max-width:900px)
    {
        .wrapper
        {
            width:60vw;
        }

        .scoreboard
        {
            width:12vw;
            height:25vh;
            margin:32vh 1vw;
        }

        .score
        {
            font-size:calc(1vh + 1vw);
        }

        .praise
        {
            font-size:calc(0.8vh + 0.8vw);
        }
    }

    @media screen and (max-width:700px)
    {
        .wrapper
        {
            display:none;
        }
    }
</style>