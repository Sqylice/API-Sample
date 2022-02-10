<template>
  <div>
      <div v-for="Employee in EmployeeData" v-bind:key="Employee.id">
          <h3>{{ Employee.employee_name }}</h3>
          <p>{{ Employee.employee_salary }}</p>
          <p>{{ Employee.employee_age }}</p>
          <!-- <img src="{{ EmployeeData.employee_img }}" alt=""> -->
      </div>
  </div>
</template>

<script>
import EmployeeData from 'http://dummy.restapiexample.com/api/v1/employees.json'

export default {
    // data() {
    //     return {

    //     }
    // }
}
</script>

<style>

</style>