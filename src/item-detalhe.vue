<template>
  <div>
    <span>{{item.text}}</span>
    <button @click="$emit('remove')">x</button>
  </div>
</template>

<script>
  export default {
    props: {
      item: Object
    }
  }
</script>