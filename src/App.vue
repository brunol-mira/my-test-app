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
<!--      <v-btn text rounded to="/">Home</v-btn>-->
<!--      <v-btn  text rounded to="/login">Login</v-btn>-->
    </v-app-bar>
    <v-content>
      <!--  Router Module -->
      <router-view></router-view>
    </v-content>
    <v-main>
<!--      <HelloWorld/>-->
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


<!--      <v-card-->
<!--          flat-->
<!--          tile-->
<!--          width="100%"-->
<!--          class="red lighten-1 text-center"-->
<!--      >-->
<!--        <v-card-text>-->
<!--          <v-btn-->
<!--              v-for="icon in icons"-->
<!--              :key="icon"-->
<!--              class="mx-4"-->
<!--              icon-->
<!--          >-->
<!--            <v-icon size="24px">-->
<!--              {{ icon }}-->
<!--            </v-icon>-->
<!--          </v-btn>-->
<!--        </v-card-text>-->

<!--        <v-divider></v-divider>-->

<!--        <v-card-text class="white&#45;&#45;text">-->
<!--          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>-->
<!--        </v-card-text>-->
<!--      </v-card>-->
      </v-layout>
    </v-footer>

<!--        <v-row-->
<!--            align="center"-->
<!--            justify="center"-->
<!--            class="ma-12"-->
<!--        >-->
<!--          <v-col-->
<!--              cols="12"-->
<!--              md="8"-->
<!--          >-->
<!--            <v-select-->
<!--                v-model="variant"-->
<!--                :items="items"-->
<!--                clearable-->
<!--                label="Variant"-->
<!--            ></v-select>-->

<!--            <v-checkbox-->
<!--                v-model="padless"-->
<!--                hide-details-->
<!--                label="Padless"-->
<!--            ></v-checkbox>-->
<!--          </v-col>-->
<!--        </v-row>-->

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
        }
      ]
    }
  }
};
</script>

