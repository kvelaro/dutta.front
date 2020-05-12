<template>
  <v-app>
    <v-content>
      <main-front></main-front>
    </v-content>
  </v-app>
</template>

<script>
import MainFront from './components/front/Main'

export default {
  name: 'App',

  components: {
    MainFront
  },

  data: () => ({
    //
  })
}
</script>
