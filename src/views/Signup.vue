<template>
  <!--  SignUp Module -->
  <v-row>
    <v-col>
      <h1>SignUp</h1>
      <v-form ref="signUpForm" v-model="formValidity">
        <v-text-field label="Email" type="email" v-model="email" :rules="emailRules" required></v-text-field>
        <v-autocomplete
            :items="browsers"
            label="Which Browser do you use ?"
        ></v-autocomplete>
        <v-file-input
            multiple
            label="Attach profile picture"
        ></v-file-input>

<!--        <v-text-field label="Birthday" v-model="birthday" type="text" readonly></v-text-field>-->
<!--        <v-row justify="center">-->
<!--          <v-date-picker v-model="birthday"></v-date-picker>-->
<!--        </v-row>-->

        <v-row justify="center">
          <v-menu
              ref="menu"
              v-model="menu"
              :close-on-content-click="false"
              :return-value.sync="date"
              transition="scale-transition"
              offset-y
              min-width="auto"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-text-field
                  v-model="birthday"
                  label="Your Birthday"
                  prepend-icon="mdi-calendar"
                  readonly
                  v-bind="attrs"
                  v-on="on"
              ></v-text-field>
            </template>
            <v-date-picker
                v-model="birthday"
                no-title
                scrollable
            >
              <v-spacer></v-spacer>
              <v-btn
                  text
                  color="primary"
                  @click="menu = false"
              >
                Cancel
              </v-btn>
              <v-btn
                  text
                  color="primary"
                  @click="$refs.menu.save(birthday)"
              >
                OK
              </v-btn>
            </v-date-picker>
          </v-menu>
        </v-row>

        <v-text-field label="Color" v-model="color" type="text" readonly></v-text-field>
        <v-row justify="center">
          <v-color-picker
              dot-size="25"
              mode="rgba"
              swatches-max-height="200"
              v-model="color"
          ></v-color-picker>
        </v-row>

        <v-checkbox label="Agree to terms & condition" v-model="agreeToTerms" :rules="agreeToTermsRules" required></v-checkbox>

        <v-btn class="mr-4" type="submit" color="primary" :disabled="!formValidity">Submit</v-btn>
        <v-btn class="mr-4" color="success" @click="validateForm">Validate Form</v-btn>
        <v-btn class="mr-4" color="warning" @click="resetFormValidation" >Reset Validation</v-btn>
        <v-btn color="error" @click="resetForm">Reset</v-btn>

      </v-form>
    </v-col>
  </v-row>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'SignPage',

  data: () => ({

    agreeToTerms: false,
    agreeToTermsRules: [
        value => !!value || 'You must agree to the term and condition to sign up for an account.',
    ],
    email: '',
    emailRules: [
      value => !!value || 'Email is required.',
      value => value.indexOf('@') !== 0 || 'Email not valid.',
      value => value.includes('@') || 'Email should include an @ symbole.',
      value => value.indexOf('.') - value.includes('@') > 1 || 'Email should contain a valid domain.',
      value => value.indexOf('.') <= value.length - 3 || 'Email should contain a valid domain extension.',
    ],
    formValidity: false,

    browsers: ['Chrome', 'Firefox', 'Safari', 'Edge', 'Brave'],
    // birthday: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
    birthday: '',
    menu: false,
    color: '',
  }),

  methods: {
    resetFormValidation() {
      this.$refs.signUpForm.resetValidation()
    },
    resetForm() {
      this.$refs.signUpForm.reset()
    },
    validateForm() {
      this.$refs.signUpForm.validate()
    }
  },
};
</script>