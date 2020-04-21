<script>
export default {
  name: 'ListComponent',
  props: {
    elements: {
      required: true,
    },
  },
}
</script>

<template>
  <div>
    <span 
      v-for="(element, index) in elements"
      :key="index"
      v-html="element.text"
      :style="{
        color: element.color,
        background: element.background,
        fontSize: element.fontSize,
      }"
      @click="$emit('changeSelected', index)"
      />
  </div>
</template>


<style scoped>
</style>
