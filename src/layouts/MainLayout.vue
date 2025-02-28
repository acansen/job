<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="transparent">
      <q-toolbar>
        <q-item-label class="text-h4 text-weight-bold" style="letter-spacing: 0.3em">
          LELO
        </q-item-label>

        <q-space />
        <q-btn
          flat
          round
          dense
          icon="search"
          class="q-mr-sm"
          size="1.2rem"
          @click="dialog = true"
        />
        <q-btn flat round dense icon="o_person" class="q-mr-sm" size="1.2rem" />
        <q-btn flat round dense icon="o_shopping_bag" size="1.2rem" />
      </q-toolbar>

      <q-dialog v-model="dialog" stack-buttons prevent-close persistent>
        <q-card class="q-py-none bg-black" style="width: 360px; max-width: 90vw">
          <q-card-section class="q-pa-none">
            <q-img src="dialog.jpg"></q-img>
            <q-btn class="absolute-top-right" flat icon="close" round v-close-popup />
          </q-card-section>
          <q-card-section class="q-pa-sm">
            <q-item-label class="text-h5 text-weight-bold" style="letter-spacing: 0.1em">
              GET OFF <br />WITH 15% OFF
            </q-item-label>
            <q-item-label class="text-white text-subtitle1">
              Be the first to know about exclusive sales, news and product releases.
            </q-item-label>
          </q-card-section>
          <q-card-section class="flex q-pa-md justify-center">
            <q-btn label="Start UP" class="text-weight-bold" outline></q-btn>
          </q-card-section>
        </q-card>
      </q-dialog>
    </q-header>
    <q-page-container style="padding: 0">
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'
const route = useRoute()
const dialog = ref(false)

onMounted(() => {
  if (route.path === '/') {
    dialog.value = true
  }
})
</script>
