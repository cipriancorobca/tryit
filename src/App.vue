<template>
  <Form :addPC="getPC" :showPop="ShowPop" />
  <Main :computers="PCs"/>
  <Popup v-show="showpopup" :delete="DeletePCs"/>
</template>

<script>
import Form from './components/Form.vue'
import Main from './components/Main.vue'
import Popup from './components/Popup.vue'
export default {
  name: 'App',
  components:{
    Form,Main,Popup,
  },
  methods:{
    getPC(pc)
    {
      const newPC = { ...pc }
      this.PCs.push(newPC)
    },
    ShowPop()
    {
      this.showpopup = true
    },
    DeletePCs(flag)
    {
      if(flag)
      {
        this.PCs = []
      }
      this.showpopup = false
    }
  },
  data(){
      return{
        PCs:[],
        showpopup:false
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
</style>
