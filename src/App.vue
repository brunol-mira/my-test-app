<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>
        My Dashboard
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
          v-for="link in links"
          :key="`${link.label}-header-link`"
          text
          rounded
          :to="link.url"
      >
        {{ link.label }}
      </v-btn>
    </v-app-bar>
    <v-content>
      <!--  Router Module -->
      <router-view></router-view>
    </v-content>
    <v-main>
      <!--  Main Module -->
    </v-main>
    <!-- footer -->
    <v-footer
        color="primary lighten-1"
        padless
    >
      <v-layout
          justify-center
          wrap
      >
        <v-btn
            v-for="link in links"
            :key="`${link.label}-footer-link`"
            color="white"
            text
            rounded
            class="my-2"
            :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-flex
          primary
          lighten-2
          py-4
          text-center
          white--text
          xs12
        >
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-flex>
      </v-layout>
    </v-footer>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    // HelloWorld,
  },

  data() {
    return {
      links: [
        {
          label: 'Home',
          url: '/'
        },
        {
          label: 'Login',
          url: '/login'
        },
        {
          label: 'Dashboard',
          url: '/dashboard'
        }
      ]
    }
  }
};
</script>

