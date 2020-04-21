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
          background: 'inherit',
          paddingLeft: element.background ? '3px' : 'inherit',
          paddingRight: element.background ? '3px' : 'inherit',
          borderRadius: element.background ? '4px' : 'inherit',
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
          text: 'My \n\nlovely',
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
      return (text || '').replace(/\n/g, '<br />')
    },
    changeSelected: function(index) {
      this.selected = index
    },
    updateText: function([index, html]) {
      this.elements[index].text = html.innerHTML.replace(/<br>/g, '\n')
    }
  },
}
</script>

<template>
  <div>
    <list-component 
    @updateText="updateText" 
    @changeSelected="changeSelected" 
    :elements="formattedElements" />
    <control-component @elUpdate="updateElement" />
    <source-component :raw-data="elements" />
  </div>
</template>


<style scoped>
</style>
