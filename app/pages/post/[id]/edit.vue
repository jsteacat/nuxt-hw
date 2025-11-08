<script lang="ts" setup>
const route = useRoute()
const postId = route.params.id
</script>

<template>
  <div>EDIT POST {{postId}}</div>
</template>
