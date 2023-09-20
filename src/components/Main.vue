<template>
    <div>
        <Block v-for="PC in computers" v-bind:key="PC.key" v-bind:cpu="PC.processor" v-bind:gpu="PC.gpu" 
               v-bind:ram="PC.ram" v-bind:storage="PC.storage" v-bind:power="PC.power"/>
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
      
    },
    props:['computers'],
  }
</script>

<style scoped>
    html,body
    {
        padding:0;
        margin:0;
    }

    div
    {
        height:auto;
        width:67.333vw;
        position:absolute;
        right:0;
        top:0;
        border-radius:18px;
        background-color: #AFE4F5;
        padding:5vh 4vw;
        overflow:auto;
        text-align: center;
        align-items: center;
        justify-content: space-evenly;
    }

    @media screen and (max-width:1298px)
    {
        div
        {
            padding:3.5vh 3.5vw;
        }
    }

    @media screen and (max-width:900px)
    {
        div
        {
            width:60vw;
        }
    }

    @media screen and (max-width:700px)
    {
        div
        {
            width:92.5%;
            position:static;
        }
    }
</style>