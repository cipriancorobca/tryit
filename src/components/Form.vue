<template>
    <div>
      <form @submit.prevent="BuildPC" @reset="ResetBuild">
        <label for="cpu">Processor</label><br>
        <select name="cpu" v-model.lazy="PCspecs.cpu">
          <option value="none" selected hidden disabled>Select a CPU</option>
          <option value="ryzen-3-1800">Ryzen 3 1800</option>
          <option value="ryzen-3-2700">Ryzen 3 2700</option>
          <option value="ryzen-5-3600">Ryzen 5 3600</option>
          <option value="ryzen-5-5500">Ryzen 5 5500</option>
          <option value="ryzen-7-4800">Ryzen 7 4800</option>
          <option value="ryzen-7-5700">Ryzen 7 5700</option>
          <option value="ryzen-9-5900">Ryzen 9 5900</option>
          <option value="threadripper-2990">Ryzen Threadripper 2990</option>
        </select><br>
        <label for="gpu">Graphics Card</label><br>
        <select name="gpu" v-model.lazy="PCspecs.gpu">
          <option value="none" selected hidden disabled>Select a Graphics Card</option>
          <option value="gtx-1060">GTX 1060</option>
          <option value="gtx-1080">GTX 1080</option>
          <option value="gtx-1660">GTX 1660</option>
          <option value="rtx-2060">RTX 2060</option>
          <option value="rtx-2080">RTX 2080</option>
          <option value="rtx-3060">RTX 3060</option>
          <option value="rtx-3090">RTX 3090</option>
          <option value="rtx-4090">RTX 4090</option>
        </select><br>
        <label for="ram">RAM</label><br>
        <select name="ram" v-model.lazy="PCspecs.ram">
          <option value="none" selected hidden disabled>Select RAM</option>
          <option value="ddr4-8gb">DDR4 8GB</option>
          <option value="ddr4-16gb">DDR4 16GB</option>
          <option value="ddr4-24gb">DDR4 24GB</option>
          <option value="ddr4-32gb">DDR4 32GB</option>
          <option value="ddr4-64gb">DDR4 64GB</option>
          <option value="ddr5-8gb">DDR5 8GB</option>
          <option value="ddr5-16gb">DDR5 16GB</option>
          <option value="ddr5-32gb">DDR5 32GB</option>
        </select><br>
        <label for="storage">Storage</label><br>
        <select name="storage" v-model.lazy="PCspecs.storage">
          <option value="none" selected hidden disabled>Select a Storage</option>
          <option value="256gb-ssd">256GB SSD</option>
          <option value="480gb-ssd">480GB SSD</option>
          <option value="980gb-ssd">980GB SSD</option>
          <option value="2tb-ssd">2TB SSD</option>
          <option value="512gb-hdd">512GB HDD</option>
          <option value="1tb-hdd">1TB HDD</option>
          <option value="2tb-hdd">2TB HDD</option>
          <option value="4tb-hdd">4TB HDD</option>
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
        PCspecs:{
          cpu:'',
          gpu:'',
          ram:'',
          storage:''
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
        var nobuild = false

        switch(this.PCspecs.cpu)
        {
          case "ryzen-3-1800":
            {
              this.PC.processor = 'Ryzen 3 1800'
              this.PCvalues.processor = 1
              break
            }
          case "ryzen-3-2700":
            {
              this.PC.processor = 'Ryzen 3 2700'
              this.PCvalues.processor = 2
              break
            }
          case "ryzen-5-3600":
            {
              this.PC.processor = 'Ryzen 5 3600'
              this.PCvalues.processor = 3
              break
            }
          case "ryzen-5-5500":
            {
              this.PC.processor = 'Ryzen 5 5500'
              this.PCvalues.processor = 4
              break
            }
          case "ryzen-7-4800":
            {
              this.PC.processor = 'Ryzen 7 4800'
              this.PCvalues.processor = 5
              break
            }
          case "ryzen-7-5700":
            {
              this.PC.processor = 'Ryzen 7 5700'
              this.PCvalues.processor = 6
              break
            }
          case "ryzen-9-5900":
            {
              this.PC.processor = 'Ryzen 9 5900'
              this.PCvalues.processor = 7
              break
            }
          case "threadripper-2990":
            {
              this.PC.processor = 'Ryzen Threadripper 2990'
              this.PCvalues.processor = 8
              break
            }
          default:
            {
              nobuild = true
            }
        }
  
        switch(this.PCspecs.gpu)
        {
          case "gtx-1060":
            {
              this.PC.gpu = 'GTX 1060'
              this.PCvalues.gpu = 1
              break
            }
          case "gtx-1080":
            {
              this.PC.gpu = 'GTX 1080'
              this.PCvalues.gpu = 2
              break
            }
          case "gtx-1660":
            {
              this.PC.gpu = 'GTX 1660'
              this.PCvalues.gpu = 3
              break
            }
          case "rtx-2060":
            {
              this.PC.gpu = 'RTX 2060'
              this.PCvalues.gpu = 4
              break
            }
          case "rtx-2080":
            {
              this.PC.gpu = 'RTX 2080'
              this.PCvalues.gpu = 5
              break
            }
          case "rtx-3060":
            {
              this.PC.gpu = 'RTX 3060'
              this.PCvalues.gpu = 6
              break
            }
          case "rtx-3090":
            {
              this.PC.gpu = 'RTX 3090'
              this.PCvalues.gpu = 7
              break
            }
          case "rtx-4090":
            {
              this.PC.gpu = 'RTX 4090'
              this.PCvalues.gpu = 8
              break
            }
          default:
            {
              nobuild = true
            }
        }
  
        switch(this.PCspecs.ram)
        {
          case "ddr4-8gb":
            {
              this.PC.ram = 'DDR4 8GB'
              this.PCvalues.ram = 1
              break
            }
          case "ddr4-16gb":
            {
              this.PC.ram = 'DDR4 16GB'
              this.PCvalues.ram = 2
              break
            }
          case "ddr5-8gb":
            {
              this.PC.ram = 'DDR5 8GB'
              this.PCvalues.ram = 3
              break
            }
          case "ddr5-16gb":
            {
              this.PC.ram = 'DDR5 16GB'
              this.PCvalues.ram = 4
              break
            }
          case "ddr4-24gb":
            {
              this.PC.ram = 'DDR4 24GB'
              this.PCvalues.ram = 5
              break
            }
          case "ddr4-32gb":
            {
              this.PC.ram = 'DDR4 32GB'
              this.PCvalues.ram = 6
              break
            }
          case "ddr5-32gb":
            {
              this.PC.ram = 'DDR5 32GB'
              this.PCvalues.ram = 7
              break
            }
          case "ddr4-64gb":
            {
              this.PC.ram = 'DDR4 64GB'
              this.PCvalues.ram = 8
              break
            }
          default:
            {
              nobuild = true
            }
        }
  
        switch(this.PCspecs.storage)
        {
          case "256gb-ssd":
            {
              this.PC.storage = '256GB SSD'
              this.PCvalues.storage = 1
              break
            }
          case "512gb-hdd":
            {
              this.PC.storage = '512GB HDD'
              this.PCvalues.storage = 2
              break
            }
          case "480gb-ssd":
            {
              this.PC.storage = '480GB SSD'
              this.PCvalues.storage = 3
              break
            }
          case "1tb-hdd":
            {
              this.PC.storage = '1TB HDD'
              this.PCvalues.storage = 4
              break
            }
          case "980gb-ssd":
            {
              this.PC.storage = '980GB SSD'
              this.PCvalues.storage = 5
              break
            }
          case "2tb-hdd":
            {
              this.PC.storage = '2TB HDD'
              this.PCvalues.storage = 6
              break
            }
          case "4tb-hdd":
            {
              this.PC.storage = '4TB HDD'
              this.PCvalues.storage = 7
              break
            }
          case "2tb-ssd":
            {
              this.PC.storage = '2TB SSD'
              this.PCvalues.storage = 8
              break
            }
          default:
            {
              nobuild = true
            }
        }
        
        if(!nobuild)
        {
          this.PC.power = Math.round((this.PCvalues.processor + this.PCvalues.gpu + 
                                      this.PCvalues.ram + this.PCvalues.storage) / 4)
          
          this.PC.key = this.index

          this.index++
          
          this.addPC(this.PC)
        }
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
        display:none;
    }

    input
    {
        margin:1vw;
        font-size:3vw;
        width:15vw;
        height:5vh;
        border-radius:25px;
        display:none;
    }

    label
    {
        font-size:4vw;
        display:none;
    }
    
    select
    {
        font-size:5vw;
        margin-bottom:4vh;
        height:5vh;
        border-radius:24px;
        text-indent:1.3vw;
        font-weight:500;
        display:none;
    }
  }
 </style>
  