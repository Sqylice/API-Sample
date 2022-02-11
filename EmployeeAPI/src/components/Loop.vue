
<script>
    import Employees from './Employees_local.vue'
    console.log(Employees);

export default {
    // data() {
    //     return {

    //     }
    // }
}
</script>
<template>
  <div>
      <p> {{ Employees }}</p>
      <div v-for="Employee in Employees" v-bind:key="Employee.id">
          <h3>{{ Employee.data.employee_name }}</h3>
          <p>{{ Employee.data.employee_salary }}</p>
          <p>{{ Employee.data.employee_age }}</p>
          <!-- <img src="{{ EmployeeData.employee_img }}" alt=""> -->
      </div>
  </div>
</template>

<style>

</style>