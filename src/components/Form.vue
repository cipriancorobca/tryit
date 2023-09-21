<template>
    <div>
      <form @submit.prevent="BuildPC" @reset="ResetBuild">
        <label for="cpu">Processor</label><br>
        <select name="cpu" v-model.number="PCvalues.processor">
          <option value="0">Select a CPU</option>
          <option value="1">Ryzen 3 1800</option>
          <option value="2">Ryzen 3 2700</option>
          <option value="3">Ryzen 5 3600</option>
          <option value="4">Ryzen 5 5500</option>
          <option value="5">Ryzen 7 4800</option>
          <option value="6">Ryzen 7 5700</option>
          <option value="7">Ryzen 9 5900</option>
          <option value="8">Ryzen Threadripper 2990</option>
        </select><br>
        <label for="gpu">Graphics Card</label><br>
        <select name="gpu" v-model.number="PCvalues.gpu">
          <option value="0">Select a Graphics Card</option>
          <option value="1">GTX 1060</option>
          <option value="2">GTX 1080</option>
          <option value="3">GTX 1660</option>
          <option value="4">RTX 2060</option>
          <option value="5">RTX 2080</option>
          <option value="6">RTX 3060</option>
          <option value="7">RTX 3090</option>
          <option value="8">RTX 4090</option>
        </select><br>
        <label for="ram">RAM</label><br>
        <select name="ram" v-model.number="PCvalues.ram">
          <option value="0">Select RAM</option>
          <option value="1">DDR4 8GB</option>
          <option value="2">DDR4 16GB</option>
          <option value="5">DDR4 24GB</option>
          <option value="6">DDR4 32GB</option>
          <option value="8">DDR4 64GB</option>
          <option value="3">DDR5 8GB</option>
          <option value="4">DDR5 16GB</option>
          <option value="7">DDR5 32GB</option>
        </select><br>
        <label for="storage">Storage</label><br>
        <select name="storage" v-model.number="PCvalues.storage">
          <option value="0">Select a Storage</option>
          <option value="1">256GB SSD</option>
          <option value="3">480GB SSD</option>
          <option value="5">980GB SSD</option>
          <option value="8">2TB SSD</option>
          <option value="2">512GB HDD</option>
          <option value="4">1TB HDD</option>
          <option value="6">2TB HDD</option>
          <option value="7">4TB HDD</option>
        </select><br>
        <input type="reset">
        <input type="submit">
      </form>
    </div>
  </template>
  
  <script>
  export default {
    name: 'BuildForm',
    emits:['add','pop'],
    props:{
      addPC:Function,
      showPop:Function,
    },
    data(){
      return{
        PCvalues:{
          processor:0,
          gpu:0,
          ram:0,
          storage:0
        },
        PC:{
          key:0,
          processor:'',
          gpu:'',
          ram:'',
          storage:'',
          power:0
        },
        index:0,
      }
    },
    methods:{
      BuildPC()
      {
        switch(this.PCvalues.processor)
        {
          case 1:
            {
              this.PC.processor = 'Ryzen 3 1800'
              break
            }
          case 2:
            {
              this.PC.processor = 'Ryzen 3 2700'
              break
            }
          case 3:
            {
              this.PC.processor = 'Ryzen 5 3600'
              break
            }
          case 4:
            {
              this.PC.processor = 'Ryzen 5 5500'
              break
            }
          case 5:
            {
              this.PC.processor = 'Ryzen 7 4800'
              break
            }
          case 6:
            {
              this.PC.processor = 'Ryzen 7 5700'
              break
            }
          case 7:
            {
              this.PC.processor = 'Ryzen 9 5900'
              break
            }
          case 8:
            {
              this.PC.processor = 'Ryzen Threadripper 2990'
              break
            }
        }
  
        switch(this.PCvalues.gpu)
        {
          case 1:
            {
              this.PC.gpu = 'GTX 1060'
              break
            }
          case 2:
            {
              this.PC.gpu = 'GTX 1080'
              break
            }
          case 3:
            {
              this.PC.gpu = 'GTX 1660'
              break
            }
          case 4:
            {
              this.PC.gpu = 'RTX 2060'
              break
            }
          case 5:
            {
              this.PC.gpu = 'RTX 2080'
              break
            }
          case 6:
            {
              this.PC.gpu = 'RTX 3060'
              break
            }
          case 7:
            {
              this.PC.gpu = 'RTX 3090'
              break
            }
          case 8:
            {
              this.PC.gpu = 'RTX 4090'
              break
            }
        }
  
        switch(this.PCvalues.ram)
        {
          case 1:
            {
              this.PC.ram = 'DDR4 8GB'
              break
            }
          case 2:
            {
              this.PC.ram = 'DDR4 16GB'
              break
            }
          case 3:
            {
              this.PC.ram = 'DDR5 8GB'
              break
            }
          case 4:
            {
              this.PC.ram = 'DDR5 16GB'
              break
            }
          case 5:
            {
              this.PC.ram = 'DDR4 24GB'
              break
            }
          case 6:
            {
              this.PC.ram = 'DDR4 32GB'
              break
            }
          case 7:
            {
              this.PC.ram = 'DDR5 32GB'
              break
            }
          case 8:
            {
              this.PC.ram = 'DDR4 64GB'
              break
            }
        }
  
        switch(this.PCvalues.storage)
        {
          case 1:
            {
              this.PC.storage = '256GB SSD'
              break
            }
          case 2:
            {
              this.PC.storage = '512GB HDD'
              break
            }
          case 3:
            {
              this.PC.storage = '480GB SSD'
              break
            }
          case 4:
            {
              this.PC.storage = '1TB HDD'
              break
            }
          case 5:
            {
              this.PC.storage = '980GB SSD'
              break
            }
          case 6:
            {
              this.PC.storage = '2TB HDD'
              break
            }
          case 7:
            {
              this.PC.storage = '4TB HDD'
              break
            }
          case 8:
            {
              this.PC.storage = '2TB SSD'
              break
            }
        }
  
        this.PC.power = Math.round((this.PCvalues.processor + this.PCvalues.gpu + 
                                    this.PCvalues.ram + this.PCvalues.storage) / 4)
        
        this.PC.key = this.index

        this.index++
        
        this.addPC(this.PC)
        //console.log('CPU:' + this.PC.processor,' GPU:' + this.PC.gpu,' RAM:' + this.PC.ram,
                    //' Storage:' + this.PC.storage,' Power rating:' + this.PC.power)
      },
  
      ResetBuild()
      {
        var selects = document.getElementsByTagName("select")
        
        for(var i = 0; i < selects.length; i++)
        {
          selects[i].selectedIndex = 0
        }

        this.showPop()
      }
    }
  }
  </script>
  
  <style>
  @import url('https://fonts.googleapis.com/css?family=Indie+Flower');
  @import url('https://fonts.googleapis.com/css?family=Kalam');
  @import url('https://fonts.googleapis.com/css?family=Architects+Daughter');

  html,body
  {
    padding:0;
    margin:0;
  }

  label
  {
    font-size:1.69vw;
    font-family:Indie Flower;
    font-weight:bold;
    color:black;
  }
  
  select
  {
    width:90%;
    font-size:2.5vh;
    margin-bottom:2.5vh;
    height:3vh;
    background-color: #FFF7EC;
    border:0.1px solid #FFF7EC;
    outline:0;
    -moz-appearance:none;
    -webkit-appearance:none;
    appearance:none;
    text-indent: 0.5vw;
    border-radius:10px;
    font-family:Architects Daughter;
    font-weight:400;
  }

  select:hover,select:focus
  {
    background-color: #FFF7EC;
    outline:0;
  }
  
  input
  {
    margin:1vw;
    font-size:1.8vh;
    width:8vw;
    height:3vh;
    background:#FFF7EC;
    border:none;
    border-radius:15px;
    font-family:Architects Daughter;
    font-weight:bold;
  }

  div
  {
    position:fixed;
    height:100%;
    width:23vw;
    text-align: center;
    margin-right:0.333vw;
    float:left;
  }

  form
  {
    margin-top:25vh;
    background-color: #FAD3C4;
    border-radius:1.69vw;
    padding:8px 0;
  }

  @media screen and (min-width:901px)
  {
    input
    {
      height:4vh;
    }

    select
    {
      height:5vh;
    }

    form
    {
      margin-top:17.5vh;
    }
  }

  @media screen and (max-width:900px)
  {
    div
    {
      width:30vw;
    }

    label
    {
      font-size:2.2vw;
    }

    select
    {
      width:95%;
      font-size:2vw;
      margin-bottom:2.5vh;
      font-weight:600;
    }
  }

  @media screen and (max-width:700px)
  {
    div
    {
        position:relative;
        margin:0;
        width:100%;
        text-align:center;
        height:75vh;
    }

    form
    {
        margin-top:0;
        padding:8px 0;
        margin:5px;
    }

    input
    {
        margin:1vw;
        font-size:3vw;
        width:15vw;
        height:5vh;
        border-radius:25px;
    }

    label
    {
        font-size:4vw;
    }
    
    select
    {
        font-size:5vw;
        margin-bottom:4vh;
        height:5vh;
        border-radius:24px;
        text-indent:1.3vw;
        font-weight:500;
    }
  }
 </style>
  