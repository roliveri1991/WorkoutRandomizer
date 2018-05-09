<template>
  <button @click="onClick">
      {{ msg }}
  </button>
</template>

<script>
export default {
  name: 'RandomButton',
  props: {
    msg: String,
    onClick: {
      type: Function,
      required: true
    }
  }
}
</script>
