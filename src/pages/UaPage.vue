<template>
  <q-page class="column flex flex-center overflow-hidden">
    {{ ua }}
  </q-page>
</template>
<script setup>
import { ref } from 'vue'
const ua = ref(navigator.userAgent)
</script>
