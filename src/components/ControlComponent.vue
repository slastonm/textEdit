
<script>
export default {
  name: 'ControlComponent',
}
</script>

<template>
  <div>
    <button @click="$emit('elUpdate', ['fontSize', '12px'])">fontSize</button>
    <button @click="$emit('elUpdate', ['color', '#FF0'])">color</button>
    <button @click="$emit('elUpdate', ['background', '#FF0'])">background</button>
  </div>
</template>


<style scoped>
</style>
