<script>
export default {
  name: 'SourceComponent',
  props: {
    rawData: {
      required: true,
    },
  },
  computed: {
    duplicatesFree: function() {
      return this.rawData.map((element, index) => {
        const newElement = { ...element }

        if (index > 0) {
          if (newElement.background === this.rawData[index - 1].background) {
            delete newElement.background
          }

          if (newElement.fontSize === this.rawData[index - 1].fontSize) {
            delete newElement.fontSize
          }

          if (newElement.color === this.rawData[index - 1].color) {
            delete newElement.color
          }
        }

        return newElement
      })
    },
  },
}
</script>

<template>
  <div>
    <h3>!Remove Duplicates</h3>
    {{ duplicatesFree }}
  </div>
</template>


<style scoped>
</style>
