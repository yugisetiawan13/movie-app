<template>
  <v-app>
    <Toolbar />
    <v-main >
      <router-view/>
    <Footer />
    </v-main>
  </v-app>
</template>

<script>
import Toolbar from '@/components/Toolbar'
import Footer from '@/components/Footer'

export default {
  name: 'App',
  components:{
    Toolbar,
    Footer,
  },

  data: () => ({
    //
  }),
};
</script>
