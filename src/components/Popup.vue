<template>
    <div class="wrapper">
        <div class="message">
            <h2>Resetting will delete all your builds.Proceed?</h2>
            <Button class="nobtn" @click="dontDelete()">No,go back</Button>
            <button class="yesbtn" @click="DeletePC()">Yes,ofc!</button>
        </div>
    </div>
  </template>
  
  <script>
  
  export default {
    name: 'MessagePopup',
    emits:['del'],
    props:{
        delete:Function
    },
    methods:{
        DeletePC()
        {
            this.delete(true)
        },
        dontDelete()
        {
            this.delete(false)
        }
    },
    data(){
        return{
          PCs:[]
        }
      },
  }
  </script>
  
  <style>
  @import url('https://fonts.googleapis.com/css?family=Kalam');
  @import url('https://fonts.googleapis.com/css?family=Indie+Flower');

  .wrapper
  {
    padding:0;
    margin:0;
    background-color:rgba(11,11,11,0.3);
    z-index: 15;
    width:100%;
    height:100%;
    text-align:center;
    vertical-align: middle;
  }

  .message
  {
    position:absolute;
    top:30%;
    left:32%;
    width:36vw;
    height:40vh;
    background:whitesmoke;
    border-radius: 24px;
  }

  h2
  {
    font-family:Kalam;
    margin-top:5vh;
    font-size: calc(1.618vh + 1.618vw);
  }

  button
  {
    width:auto;
    font-size:calc(1.4vh + 1.4vw);
    font-family:Indie Flower;
    letter-spacing:2px;
    border-radius:calc(1.4vh + 1.4vw);
    margin-top:7vh;
    vertical-align: middle;
  }

  .yesbtn
  {
    margin-left:5vw;
    font-weight: 700;
    background-color: #17d6cd;
    color:white;
    border:1.33px solid #17d6cd;
    transition: 0.3s;
  }

  .nobtn
  {
    background-color: #AE445A;
    color:white;
    border:1.33px solid #AE445A;
    font-weight:100;
    transition: 0.3s;
  }

  .yesbtn:hover
  {
    background-color: #15bbb3;
    border:1.33px solid #15bbb3;
  }

  .nobtn:hover
  {
    background-color: #883646;
    border:1.33px solid #883646;
  }

  @media screen and (max-width:800px)
  {
    .message
    {
        height:auto;
        padding-bottom:4vh;
    }

    h2
    {
        margin-top:4vh;
        font-size: calc(1.4vh + 1.4vw);
    }

    button
    {
        font-size:calc(1.2vh + 1.2vw);
    }

    .yesbtn
    {
        margin-left:3vw;
    }
  }

  @media screen and (max-width:700px)
  {
    .wrapper
    {
        position:absolute;
        top:0;
        height:100vh;
    }
  }
  </style>