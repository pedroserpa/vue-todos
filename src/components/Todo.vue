<script setup>
const props = defineProps(['title', 'status'])
defineEmits(['change-status'])
</script>

<template>
  <li>
      <span class="title">{{ title }}</span><button type="button" @click="$emit('change-status')">&times</button>
    </li>
</template>

<style scoped>
li {width:100%; padding: 12px 0;}
li.lnthrough span.title {text-decoration: line-through;}
li button {float: right; background-color: transparent; border:1px solid #eaeaea; border-radius:50%; color:#eaeaea; cursor: pointer;}
</style>