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

      <v-btn @click="toggleTheme" text rounded>Toggle Theme</v-btn>

<!--      <v-container-->
<!--          class="px-0"-->
<!--          fluid-->
<!--      >-->
<!--        <v-switch-->
<!--            @click="toggleTheme"-->
<!--        ></v-switch>-->
<!--      </v-container>-->

    </v-app-bar>
    <v-main>
      <v-container >
        <!--  Router Module -->
        <router-view></router-view>
      </v-container>
    </v-main>
<!--    <v-main>-->
<!--      &lt;!&ndash;  Main Module &ndash;&gt;-->
<!--    </v-main>-->
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
        },
        {
          label: 'Listing',
          url: '/employees'
        },
        {
          label: 'Signup',
          url: '/signup'
        },
      ]
    }
  },

  methods: {
    toggleTheme() {
      this.$vuetify.theme.themes.dark.anchor = '#41B883'
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    },
  }
};
</script>

