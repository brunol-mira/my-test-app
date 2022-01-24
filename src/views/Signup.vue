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

        <v-text-field label="Birthday" v-model="birthday" type="text" readonly></v-text-field>
        <v-row justify="center">
          <v-date-picker v-model="birthday"></v-date-picker>
        </v-row>

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
  }),

};
</script>