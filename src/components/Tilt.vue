<template>
    <div>
        <h1>Attention!</h1>
        <img src="../assets/phone.png">
        <p>
            The game cannot be played with phone held vertically.
            Tilt your phone and enjoy :)
        </p>
    </div>
</template>

<script>

export default {
    name:'TiltYoPhone',
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Kalam');
    div
    {
        width:80vw;
        height:84vh;
        position:absolute;
        background:white;
        border-radius: 24px;
        top:10%;
        left:10%;
        display:none;
    }
    
    h1
    {
        font-family:Kalam;
        font-size: calc(4vh + 4vw);
        font-weight:bold;
        margin-bottom:2vh;
    }

    p
    {
        font-family:Kalam;
        font-size: calc(2.5vh + 2.5vw);
        font-weight:bold;
        margin-top:8vh;
    }

    img
    {
        width:auto;
        height:25vh;
    }

    @media screen and (max-width:700px)
    {
        div
        {
            display:block;
        }
    }
</style>