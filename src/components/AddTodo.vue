<script setup>
const title = defineModel('title')

defineEmits(['add-item'])

</script>
<template>
<input type="text" v-model="title" placeholder="New Item" />
    <br>
    <button type="button" @click="$emit('add-item')">Add</button>
  <br>
</template>

<style scoped>
button{padding:8px 22px; background: #63bf63; border:none; cursor: pointer;}
</style>