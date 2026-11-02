<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title class="text-h4"> Knjižnica </q-toolbar-title>

        <div>Quasar v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Essential Links </q-item-label>

        <EssentialLink
          v-for="link in linksList"
          :key="link.label"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from '@/components/EssentialLink.vue'

const linksList = [
  {
    label: 'Naslovna',
    caption: 'quasar.dev',
    icon: 'school',
    link: '#/'
  },
  {
    label: 'Popis svih knjiga',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: '#/popis_knjiga'
  },
  {
    label: 'Pretraživanje',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: '#/pretrazivanje'
  },
  {
    label: 'O nama',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: '#/o_nama'
  },
  {
    label: 'Lokacija',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: '#/lokacija'
  },
  {
    label: 'Log in',
    caption: '@QuasarFramework',
    icon: 'login',
    link: '#/login'
  },
  {
    label: 'Registracija',
    caption: 'Community Quasar projects',
    icon: 'exit_to_app',
    link: '#/registracija'
  }
]

const leftDrawerOpen = ref(false)

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>
