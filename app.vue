<script setup>
import { ref } from 'vue'

const { locale } = useI18n()

const leftDrawerOpen = ref(false)
const rightDrawerOpen = ref(false)

function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}

function toggleRightDrawer () {
  rightDrawerOpen.value = !rightDrawerOpen.value
}
</script>

<template>
  <div>
    <q-layout view="hHh LpR fff">

      <q-header elevated class="bg-primary text-white" height-hint="98">
        <q-toolbar align="center">
          <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />

          <q-toolbar-title>
            <q-avatar>
              <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
            </q-avatar>
            Title
          </q-toolbar-title>

          <q-select dense dark v-model="locale" :options="['en', 'fr', 'cz']" />        

          <q-btn dense flat round icon="menu" @click="toggleRightDrawer" />
        </q-toolbar>

        <q-tabs align="center">
          <q-route-tab to="/" label="Index" />
          <q-route-tab to="/content" label="content" />
          <q-route-tab to="/contact" label="contact" />
        </q-tabs>
      </q-header>

      <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
        <!-- drawer content -->
      </q-drawer>

      <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
        <!-- drawer content -->
      </q-drawer>

      <q-page-container>
        <router-view />
      </q-page-container>

      <q-footer elevated class="bg-grey-8 text-white">
        <q-toolbar>
          <q-toolbar-title>
            <q-avatar>
              <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
            </q-avatar>
            <div>Title</div>
          </q-toolbar-title>
        </q-toolbar>
      </q-footer>

    </q-layout>
  </div>
</template>

