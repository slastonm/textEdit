<template>
  <div id="app">
    <EditList :list="textBlocks"></EditList>
      <!-- <pre>{{$data |json }}</pre> -->
  </div>
</template>

<script>
import EditList from './components/EditListComponent'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    EditList,
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
          text:'<br/>',
        },
        {
          text:'My lovely',
          backgroundColor: 'rgb(248, 187, 208)',
          color:'#fff'
        },
        {
          text:'little',
          color:'rgb(136, 14, 79)',
          fontSize:54
        },
        {
          text:'Ponny',
          backgroundColor: 'rgb(248, 187, 0)',
          color:'rgb(186, 104, 200)'
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
