<template>
  <Showins :ins="ShowIns"/>
  <Form :addPC="getPC" :showPop="ShowPop" />
  <Main :computer="this.PC" :matchme="this.matchMe" :nextPC="NextStep" :score="this.score" :praise="this.praiseText"/>
  <Popup v-show="showpopup" :delete="DeletePCs"/>
  <Tilt/>
  <Instructions v-show="showInstructions" :ins="HideIns"/>
</template>

<script>
import Form from './components/Form.vue'
import Main from './components/Main.vue'
import Popup from './components/Popup.vue'
import Tilt from './components/Tilt.vue'
import Instructions from './components/Instructions.vue'
import Showins from './components/Insbtn.vue'
export default {
  name: 'App',
  components:{
    Form,Main,Popup,Tilt,Instructions,Showins
  },
  methods:{
    getPC(pc)
    {
      this.PC = { ...pc }
      this.nextAllow = true
      if(this.matchMe%2 == 0)
      {
        if(this.PC.power == this.matchMe)
        {
          this.score += 10
          this.praiseText = 'Well done'
        }

        else if(this.PC.power == this.matchMe-1)
        {
          this.score += 5
          this.praiseText = "I'll take that"
        }

        else
        {
          this.praiseText = "Better luck next time"
        }
      }

      else
      {
        if(this.PC.power == this.matchMe)
        {
          this.score += 10
          this.praiseText = 'Well done'
        }

        else if(this.PC.power == this.matchMe+1)
        {
          this.score += 5
          this.praiseText = "I'll take that"
        }

        else
        {
          this.praiseText = "Better luck next time"
        }
      }
    },
    ShowPop()
    {
      this.showpopup = true
    },
    DeletePCs(flag)
    {
      this.showpopup = false
      if(flag)
      {
        this.score = 0
        this.nextAllow = false
        this.praiseText = ''
        if(this.PC.power != 0)
        {
          this.PC = this.initPC
        }
      }
    },
    ShowIns()
    {
      this.showInstructions = true
    },
    HideIns()
    {
      this.showInstructions = false
    },
    NextStep()
    {
      if(this.nextAllow)
      {
        let temp

        do
        {
          temp = this.matchMe
          this.matchMe = Math.round(Math.random()*7+1)
        }while(this.matchMe == temp)
        
        this.praiseText = ''
        if(this.PC.power != 0)
        {
          this.PC = this.initPC
        }
        this.nextAllow = false
      }
    }
  },
  data(){
      return{
        PC:{
          key:0,
          processor:'',
          gpu:'',
          ram:'',
          storage:'',
          power:0
        },
        initPC:{
          key:0,
          processor:'',
          gpu:'',
          ram:'',
          storage:'',
          power:0
        },
        showpopup:false,
        matchMe:Math.round(Math.random()*7+1),
        score:0,
        praiseText:'',
        nextAllow:false,
        showInstructions:false
      }
    },
}
</script>

<style>
html,body
{
  padding:0;
  margin:0;
}

#app {
  position:relative;
  width:100%;
  padding:0;
  margin:0;
}

@media screen and (max-width:700px)
{
  html,body
  {
    background-color:rgba(121, 121, 121, 0.3);
  }
}
</style>
