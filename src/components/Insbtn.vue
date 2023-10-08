<template>
    <button class="instruction" @click="ins()">How to play?</button>
</template>

<script>
export default{
    name:'ShowInstructionsButton',
    props:{
        ins:Function,
    }
}
</script>

<style scoped>
.instruction
{
  height:50px;
  border-radius:8px;
  position:fixed;
  top:-5.5vh;
  left:12px;
  border:none;
  background-color:#AFE4F5;
  font-family: Kalam;
  font-size:calc(0.8vh + 0.8vw);
  z-index: 3;
}

.instruction:active
{
  top:-48px;
}

@media screen and (max-width:700px)
{
  .instruction
  {
    display:none;
  }
}
</style>