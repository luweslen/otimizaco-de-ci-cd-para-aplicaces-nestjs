<script setup lang="ts">
import { computed, ref } from 'vue'
import BirdColorful from './BirdColorful.vue'

const props = withDefaults(
  defineProps<{
    color?: string
    width?: string
    height?: string
  }>(),
  {
    color: '#ffffff',
    width: '32px',
    height: '32px',
  },
)

const isOver = ref(true)

const width = computed(() => props.width)
const height = computed(() => props.height.replace('px', ''))
</script>

<template>
  <div class="size-auto">
    <a href="https://zrp.com.br" target="_blank" class="size-full">
      <svg class="cursor-pointer"  v-if="isOver" @mouseenter="isOver = false" xmlns="http://www.w3.org/2000/svg" :width="width" :height="height" viewBox="0 0 257 196" fill="none">
        <path d="M199.101 139.733L197.624 141.386C181.278 160.542 157.351 171.53 131.946 171.53C130.469 171.53 128.894 171.53 127.417 171.433V184.949L111.367 169.099C93.1501 164.626 76.706 154.222 64.89 139.733C52.5815 124.564 44.2118 105.992 44.2118 86.5443C44.2118 50.1776 69.5179 18.2837 104.277 6.51802L105.262 6.22632L106.148 6.71251C119.244 13.9081 127.318 27.6185 127.318 42.3013V68.9444L199.101 139.733Z" :fill="color"/>
        <path d="M257 173.183L254.932 174.933C221.059 204.299 169.364 202.84 137.461 171.335C124.266 158.305 115.995 141.678 113.238 123.494C110.678 105.894 113.927 87.6138 122.198 72.0559L122.691 71.1807L123.675 70.889C137.953 67.0968 153.413 70.9862 163.85 81.2934L257 173.183Z" :fill="color"/>
        <path d="M118.85 65.4438C107.231 78.9598 93.2485 81.0991 83.4018 81.0018H83.3032H83.2049L0 80.1267L56.1264 14.1025C56.5202 13.4219 60.9512 7.58761 68.3362 3.89259C73.2596 1.46165 82.7126 -0.969256 91.5746 0.392067C91.5746 0.392067 122.69 3.69814 127.121 35.8837C128.795 47.9411 124.561 58.7345 118.85 65.4438Z" :fill="color"/>
      </svg>
      <BirdColorful class="cursor-pointer" v-else @mouseleave="isOver = true" :width="width" :height="height" />
    </a>
  </div>
</template>

<style scoped>
a {
  border-bottom-width: 0px;
  border-color: none;
  border-style: none;
}
</style>
