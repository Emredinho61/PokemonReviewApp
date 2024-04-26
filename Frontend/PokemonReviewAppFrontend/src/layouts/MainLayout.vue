<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn flat dense round icon="menu" aria-label="Menu" @click="toggleLeftDrawer" />

        <q-toolbar-title>
          Pokemon Review App
        </q-toolbar-title>

        <div>v{{ $q.version }}</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header>
          Some Links
        </q-item-label>

        <EssentialLink v-for="link in linksList" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
      <CarouselOptions></CarouselOptions>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'
import CarouselOptions from 'components/CarouselOptions.vue'

const linksList = [
  {
    title: 'Github',
    caption: 'Github link to this project',
    icon: 'code',
    link: 'https://github.com/Emredinho61/pokemonReviewApp/'
  },
  {
    title: 'LinkedIn',
    caption: 'My LinkedIn profile',
    icon: 'person',
    link: 'https://linkedin.com/in/emre-bayazitoglu'
  },
  {
    title: 'YouTube Tutorial',
    caption: 'YouTube Tutorial to Backend',
    icon: 'play_circle_filled',
    link: 'https://www.youtube.com/playlist?list=PL82C6-O4XrHdiS10BLh23x71ve9mQCln0'
  }
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    EssentialLink,
    CarouselOptions
  },

  data() {
    return {
      linksList,
      leftDrawerOpen: false
    }
  },

  methods: {
    toggleLeftDrawer() {
      this.leftDrawerOpen = !this.leftDrawerOpen
    }
  }
})
</script>
