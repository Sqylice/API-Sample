<template>
  <p></p>
</template>

<script>
// Importing array from local JSON file for testing
import json from "C:/Code/Mina-Egna-Grejs/Employee-API/EmployeeAPI/API-Sample/EmployeeAPI/data/employees.json"
console.log(json.status)
export default {
    name: 'EmployeeData',
    data: function(){
        return{
            Employees: json.data
        };
    },
    mounted: function(){
        // Checking if everything works
    console.log(this.Employees);
    }
}
</script>

<style>

</style>