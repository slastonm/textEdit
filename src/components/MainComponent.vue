<script>
import ListComponent from './ListComponent'
import ControlComponent from './ControlComponent'
import SourceComponent from './SourceComponent'

export default {
  name: 'MainComponent',
  components: {
    ListComponent,
    ControlComponent,
    SourceComponent,
  },
  computed: {
    formattedElements: function() {
      return this.elements.map(element => {
        return {
          color: 'inherit',
          fontSize: '12px',
          'background-color': 'inherit',
          ...element,
          text: this.formatText(element.text),
        }
      })
    },
  },
  data: function() {
    return {
      selected: 0,
      elements: [
        {
          text: 'ko',
        },
        {
          text: 'ok',
          background: '#FF0',
        },
        {
          text: 'ok',
          background: '#FF0',
        },
        {
          text: 'My \nlovely',
          fontSize: '16px',
          color: '#F00',
        },
        {
          text: 'My lovely',
          fontSize: '16px',
          color: '#F00',
        },
      ],
    }
  },
  methods: {
    updateElement([property, value]) {
      const elements = JSON.parse(JSON.stringify(this.elements))

      if (elements[this.selected][property]) {
        delete elements[this.selected][property]
      } else {
        elements[this.selected][property] = value
      }

      this.$set(this, 'elements', elements)
    },
    formatText: function(text) {
      return text.replace('\n', '<br/>')
    },
    changeSelected: function(index) {
      this.selected = index
    },
  },
}
</script>

<template>
  <div>
    <h1>{{selected}}</h1>
    <list-component @changeSelected="changeSelected" :elements="formattedElements" />
    <control-component @elUpdate="updateElement" />
    <input v-model="elements[0].text" />
    <source-component :raw-data="elements" />
  </div>
</template>


<style scoped>
</style>
