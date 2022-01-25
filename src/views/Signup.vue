<template>
  <!--  SignUp Module -->
  <v-row>
    <v-col>
      <h1>SignUp</h1>
      <v-form>
        <v-text-field label="Email" type="email"></v-text-field>
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

        <v-checkbox label="Agree to terms & condition"></v-checkbox>

        <v-btn type="submit" color="primary">Submit</v-btn>

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
    browsers: ['Chrome', 'Firefox', 'Safari', 'Edge', 'Brave'],
    // birthday: (new Date(Date.now() - (new Date()).getTimezoneOffset() * 60000)).toISOString().substr(0, 10),
    birthday: '',
    menu: false,
    color: '',
  }),

};
</script>




















<!--<template>-->
<!--  <v-row>-->
<!--    <v-col-->
<!--        cols="12"-->
<!--        sm="6"-->
<!--        md="4"-->
<!--    >-->
<!--      <v-menu-->
<!--          ref="menu"-->
<!--          v-model="menu"-->
<!--          :close-on-content-click="false"-->
<!--          :return-value.sync="date"-->
<!--          transition="scale-transition"-->
<!--          offset-y-->
<!--          min-width="auto"-->
<!--      >-->
<!--        <template v-slot:activator="{ on, attrs }">-->
<!--          <v-text-field-->
<!--              v-model="date"-->
<!--              label="Picker in menu"-->
<!--              prepend-icon="mdi-calendar"-->
<!--              readonly-->
<!--              v-bind="attrs"-->
<!--              v-on="on"-->
<!--          ></v-text-field>-->
<!--        </template>-->
<!--        <v-date-picker-->
<!--            v-model="date"-->
<!--            no-title-->
<!--            scrollable-->
<!--        >-->
<!--          <v-spacer></v-spacer>-->
<!--          <v-btn-->
<!--              text-->
<!--              color="primary"-->
<!--              @click="menu = false"-->
<!--          >-->
<!--            Cancel-->
<!--          </v-btn>-->
<!--          <v-btn-->
<!--              text-->
<!--              color="primary"-->
<!--              @click="$refs.menu.save(date)"-->
<!--          >-->
<!--            OK-->
<!--          </v-btn>-->
<!--        </v-date-picker>-->
<!--      </v-menu>-->
<!--    </v-col>-->
<!--  </v-row>-->
<!--</template>-->