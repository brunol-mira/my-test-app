<template>
  <div>
    <h1>Dashboard</h1>
    <v-data-table
        :headers="headers"
        :items="employees"
        :items-per-page="5"
        class="elevation-1"
        @click:row="SelectRow"
        :multi-sort="true"
    ></v-data-table>

    <v-snackbar v-model="snackbar">
      You have selected {{ selectedEmployee.name }},
      {{ selectedEmployee.title }}
      <v-btn color="pink" text @click="snackbar = false">
        Close
      </v-btn>
    </v-snackbar>

  </div>
</template>

<script>
import employeesData from '../data/employees.json'
// console.log(JSON.stringify(employeesData));

export default {
  data () {
    return {
      selectedEmployee: {
        name: '',
        title: ''
      },
      snackbar: false,
      headers: [
        { text: 'Employee ID', value: 'id'},
        { text: 'Name', value: 'name' },
        { text: 'Position Title', value: 'title' },
        { text: 'Salary', value: 'salary' }
      ],
      employees: employeesData
    }
  },
  methods: {
    SelectRow(event) {
      this.snackbar = true;
      // this.currentItem = event.name;
      this.selectedEmployee.name = event.name;
      this.selectedEmployee.title  = event.title;
    }
  }
}
</script>
