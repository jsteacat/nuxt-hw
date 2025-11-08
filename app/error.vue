<script lang="ts" setup>
import type { NuxtError } from '#app'
import ActionButton from '~/components/ActionButton.vue'

const { error } = defineProps<{
  error: NuxtError
}>()
</script>

<template>
  <div class="error-page">
    <h1 class="title">{{ error.statusCode }}</h1>
    <div v-if="error.statusCode === 404" class="message">Страница не найдена, вернитесь на главную страницу</div>
    <div v-else class="message">{{ error.statusMessage }}</div>
    <div class="button-container">
      <ActionButton full-size @click="navigateTo('/')">
        Главная страница
      </ActionButton>
    </div>
  </div>
</template>

<style scoped>
.error-page {
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.title {
  font-size: 120px;
  line-height: 100%;
  font-weight: 500;
}

.message {
  font-size: 16px;
  line-height: 24px;
  font-weight: 300;
  margin-bottom: 24px;
}

.button-container {
  width: 300px;
}
</style>

