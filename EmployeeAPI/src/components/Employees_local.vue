<template>
  <p></p>
</template>

<script>
// Importing array from local JSON file for testing
import json from "@/data/employees.json"
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