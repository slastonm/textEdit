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
        paddingLeft: element.paddingLeft,
        paddingRight: element.paddingRight,
        borderRadius: element.borderRadius,
      }"
      @click="$emit('changeSelected', index)"
      contenteditable="true" 
      @input="$emit('updateText', [index, $event.target])"
    />
  </div>
</template>


<style scoped>
</style>
