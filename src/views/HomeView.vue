<template>
  <v-app  :style="{background: $vuetify.theme.themes.dark.background}">
    <Movie />
  </v-app>
</template>

<script>
/* eslint-disable */
  import Movie from '../components/Movie'

  export default {
    name: 'HomeView',

    components: {
      Movie,
    },
  }
</script>
