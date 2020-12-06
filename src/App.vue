<template>
  <input type="text" v-model="foo">
  <button type="button" @click="emitFoo">Click</button>
</template>

<script setup>
  import { defineEmit, defineProps, ref } from 'vue'

  const emit = defineEmit(['foo'])

  const foo = ref('')

  const emitFoo = () => {
    console.log(`Emitting 'foo' with value '${foo.value}'`)
    emit('foo', foo.value)
  }
</script>