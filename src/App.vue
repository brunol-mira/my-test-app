<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>
        My Dashboard
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn text rounded>Home</v-btn>
      <v-btn  text rounded>Login</v-btn>
    </v-app-bar>
    <v-content>
      <!--  Login Module -->
      <v-card width="400" class="mx-auto mt-5">
        <v-card-title>
          <h1 class="display-1">Login</h1>
        </v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field
                label="Username"
                prepend-icon="mdi-account-circle"
            />
            <v-text-field
                :type="showPassword ? 'text' : 'password'"
                label="Password"
                prepend-icon="mdi-lock"
                :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
                @click:append="showPassword = !showPassword"
            />
          </v-form>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn color="success">
            Register
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn color="info">
            Login
          </v-btn>
        </v-card-actions>
      </v-card>
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
            :key="link"
            color="white"
            text
            rounded
            class="my-2"
        >
          {{ link }}
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

  data: () => ({
    showPassword: false,
    links: ['Home', 'Login'],
  }),
};
</script>

