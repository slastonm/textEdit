<template>
  <div class="container" spellcheck="false">
    <div class="controls">
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

    <TextBlock v-for="item in list" 
    :key="item.text"
    :msg="item.text"
    :color="item.color"
    :background="item.backgroundColor"
    :fontsize="item.fontSize"
    />
  </div>

</template>

<script>
import TextBlock from './TextBlock.vue'

export default {
  name: 'EditList',
  components: {
    TextBlock,
  },
  props: ['list'],
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

<style scoped>
.container{
  color: rgb(255, 255, 255);
  opacity: 1;
  border-radius: 6px;
  transform: rotate(0deg);
  border: 0px solid rgb(70, 144, 247);
  padding: 10px;
  text-align: center;
  letter-spacing: 0px;
  font-size: 32px;
  font-family: Aleo;
  font-weight: 300;
  text-decoration: none;
  box-shadow: rgb(0, 0, 0) 0px 0px 0px 0px;
  text-transform: initial;
  font-style: normal;
  z-index: 2002;
  text-shadow: rgba(0, 0, 0, 0.2) 2px 2px 0px;
  line-height: 1.5em;
}

</style>
