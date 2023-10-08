<template>
    <div class="wrapper">
        <div class="content">
            <button @click="ins()">✖</button><br>
            <img src="../assets/try_it_instructions.gif">
            <p>Watch this as many times as you need</p>
        </div>
    </div>
</template>

<script>
export default{
    name:'GameInstructions',
    props:{
        ins:Function,
    }
}
</script>

<style scoped>
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

  .content
  {
    position:absolute;
    top:15.5%;
    left:25%;
    width:50vw;
    height:69vh;
    background:whitesmoke;
    border-radius: 24px;
  }

  img
  {
    margin-top:2vh;
    width:40vw;
    height:auto;
  }

  button
  {
    margin-top:-2.69vh;
    margin-left:47.5vw;
    position:relative;
    font-family:Arial;
    border:2px solid black;
  }

  button:hover
  {
    background-color: rgb(207, 207, 207);
  }

  button:active
  {
    background-color: rgb(189, 189, 189);
  }

  p
  {
    font-family:Indie Flower;
    font-weight: bold;
    font-size: calc(1vh + 1vw);
  }

  @media screen and (min-aspect-ratio:18/10)
  {
    .content
    {
        top:10%;
        left:25%;
        width:50vw;
        height:80vh;
    }
  }

  @media screen and (min-aspect-ratio:2/1)
  {
    img
    {
        width:35vw;
        height:auto;
        margin-top:1vh;
    }
  }
</style>