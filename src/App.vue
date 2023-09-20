<template>
  <Form :addPC="getPC" />
  <Main :computers="PCs"/>
</template>

<script>
import Form from './components/Form.vue'
import Main from './components/Main.vue'
export default {
  name: 'App',
  components:{
    Form,Main,
  },
  methods:{
    getPC(pc)
    {
      const newPC = { ...pc }
      this.PCs.push(newPC)
      console.log(this.PCs)
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
