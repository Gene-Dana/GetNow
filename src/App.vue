<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase" justify-center>
        <span>Pro</span>
        <span class="font-weight-light">Desk </span>
        
      </v-toolbar-title>
      <!-- <v-spacer></v-spacer>
      <v-btn
        flat
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
      >
        <span class="mr-2">Latest Release</span>
      </v-btn> -->
    </v-toolbar>

    <v-content>
      <InputForm/>
    </v-content>
  </v-app>
</template>

<script>

import InputForm from './components/InputForm'

export default {
  name: 'App',
  components: {
 
    InputForm
  },
  data () {
    return { 
      //
    }
  }
}
</script>
