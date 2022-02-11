<template>
  <div>
      <!-- <p> {{EmployeeData}} </p> -->
      <div v-for="Employee in EmployeeData" v-bind:key="Employee.id">
          <h3>{{ Employee.employee_name }}</h3>
          <p>{{ Employee.employee_salary }}</p>
          <p>{{ Employee.employee_age }}</p>
          <!-- <img src="{{ EmployeeData.employee_img }}" alt=""> -->
      </div>
  </div>
</template>

<script>
    import json from "@/data/employees.json"
    // import Employees from './Employees_local.vue'
    console.log(json);

export default {
    data() {
        return {
            EmployeeData: json.data
        }
    }
}
</script>

<style>

</style>