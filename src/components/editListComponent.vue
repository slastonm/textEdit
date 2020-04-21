<template>
  <div class="container" spellcheck="false"></div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: {
      default: '',
    },
    color: {
      type: String,
      default: 'black',
    },
    background: {
      type: String,
      default: 'red',
    },
    fontSize: {
      type: Number,
      default: 12,
    },
  },
  mounted: function() {
    this.$el.innerText = this.msg
  },

  methods: {
    update(event) {
      console.log(event)
      this.$emit('update', event.target)
    },
  },
}
</script>

<style scoped>
.container {
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
