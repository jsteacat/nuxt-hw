<script lang="ts" setup>
const { fullSize } = defineProps<{
  fullSize?: boolean
}>()
</script>

<template>
  <button :class="['button', fullSize && 'full-size']">
    <slot />
  </button>
</template>

<style scoped>
.button {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 24px;
  background-color: var(--color-black);
  border: 1px solid var(--color-black);
  border-radius: 20px;
  font-size: 16px;
  font-weight: 500;
  color: var(--color-white);
  cursor: pointer;
}

.button:hover {
  background-color: var(--color-black-hover);
}

.button.full-size {
  width: 100%;
}
</style>
