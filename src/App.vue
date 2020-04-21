<template>
  <div id="app">
    <main-component/>
    <!-- <div class="controls">
      <button @click="changeColor">
        Change color
      </button>
      <button @click="changeFontSize">
        Change font size
      </button>
      <button @click="changeBackground">
        Change background
      </button>
    </div>
    <HelloWorld :msg="msg"  @update="msg = $event"/>
    <div>
      {{$data}}
      <pre>{{$data |json }}</pre>
    </div> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import MainComponent from './components/MainComponent.vue'

export default {
  name: 'App',
  components: {
    MainComponent
  },
  data: function () {
    return {
      textBlocks:[
        {
          text:'Hi',
          backgroundColor: 'rgb(248, 187, 208)',
          color:'#fff'
        },
        {
          text:'My lovely',
          backgroundColor: 'rgb(248, 187, 208)',
          color:'#fff'
        },
        {
          text:'little',
          backgroundColor: 'rgb(248, 187, 208)',
          color:'#fff'
        },
      ]
    }
  },
  methods: {
    changeColor(){
      if(this.color === 'red'){
        this.color = 'black'
      }
      this.color = 'red'
    },
    changeFontSize(){
      this.fontSize =this.fontSize+1
    },
    changeBackground(){
      if (this.background === 'black'){
        this.background = '' 
      }
      this.background = 'white' 
    }
  }
}

</script>

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.controls{
  text-align: center;
}
.controls button{
  text-align: center;
  padding: 5px;
  margin: 0 5px;
  font-size: 16px;
  border-radius: 4px;
}
.controls button:hover{
  background-color: #ccc;
}
</style>
