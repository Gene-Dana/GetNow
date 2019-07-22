<template>
  <v-app>
    <v-toolbar app>
    
       <v-img :src="require('./assets/ProDeskLogo_1.png')" contain height="12vh"></v-img>
     
    
      <v-spacer></v-spacer>
      <v-btn
       block
        color=blue
        
      >
      <div class="text-truncate" style="font-size: .60em"> 
        Speak with a <br /> representative <br /> <div class="font-weight-bold" style="font-size: 1.2em"> +1 877-342-4747 </div>

        </div>
        
        
   <!-- <v-img :src="require('./assets/toolbar-buttone.png')"></v-img> -->
      </v-btn>
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
  metaInfo: {
      title: 'My Example App',
      titleTemplate: '%s - Yay!',
      htmlAttrs: {
        lang: 'en',
        amp: true
      }
    },
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
