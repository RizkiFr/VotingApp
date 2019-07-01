<template>
  <v-app>
    <v-toolbar app dark class="cyan">
      <v-toolbar-title class="headline text-uppercase">
        <span>Si</span>
        <span class="font-weight-light">Netral</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>

    <v-content>
      <HelloWorld/>
    </v-content>
    <v-footer dark height="auto">
      <v-card flat tile class="cyan flex text-xs-center">
          <v-card-text flat>
            Made with
            <v-icon small>favorite</v-icon>
            by: Rizki Fr.
          </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
      //
    }
  }
}
</script>
