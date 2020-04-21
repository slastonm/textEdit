<template>
  <span 
  :style="{ backgroundColor: background, color: color, fontSize: `${fontsize}px`}"
  :class="{'border-radius-style': background,  '': !background}"
  contenteditable="true" >
  </span>
</template>

<script>
export default {
  name: 'TextBlock',
  props: {
    msg: {
      type: String,
      default: ''
    },
    color: {
      type: String,
      default: ''
    },
    background: {
      type: String,
      default: ''
    },
    fontsize: {
      type: Number,
      default: 32
    }
  },
  mounted:function(){
    this.$el.innerHTML = this.msg;
  },

  methods: {

  }
}
</script>

<style scoped>
  span{
    padding-left:3px;
    padding-right: 3px;
  }
  .border-radius-style{
    border-radius: 6px;
  }
</style>
