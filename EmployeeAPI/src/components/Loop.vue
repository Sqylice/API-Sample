<template>
    <div v-if="EmployeeData.length">
        <div v-for="Employee in EmployeeData" v-bind:key="Employee.id">
            <div class="card" style="width: 15rem;">
                <!-- As no images are in the file, this isn't strictly necessary but it's nice to have -->
                <!-- <img class="card-img-top" src="{{ Employee.profile_image }}" alt="A profile picture of the employee"> -->
                <div class="card-body bg-dark">
                    <h5 class="card-title">{{ Employee.employee_name }}</h5>
                    <p class="card-text">Salary: {{ Employee.employee_salary }}</p>
                    <p class="card-text">Age: {{ Employee.employee_age }}</p>
                </div>
            </div>
        </div>
    </div>
    <div v-else>
        <div v-for="Employee in EmployeeBackUpData" v-bind:key="Employee.id">
            <div class="card" style="width: 15rem;">
                <!-- As no images are in the file, this isn't strictly necessary but it's nice to have
                <img class="card-img-top" src="{{ Employee.profile_image }}" alt="A profile picture of the employee"> -->
                <div class="card-body bg-dark">
                    <h5 class="card-title">{{ Employee.employee_name }}</h5>
                    <p class="card-text">Salary: {{ Employee.employee_salary }}</p>
                    <p class="card-text">Age: {{ Employee.employee_age }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
//Pull axios to work with
import axios from 'axios'
//Pull the local .json file for redundancy
import json from "@/data/employees.json"

export default {
    data () {
    return {
        //Default Null value to be overwritten
        EmployeeData: [],
        // Feeding the back up just in case
        EmployeeBackUpData: json.data
    }
  },
  mounted () {
    axios
        .get('http://dummy.restapiexample.com/api/v1/employees')
        .then(response => (this.EmployeeData = response.data.data))
        console.log(this.EmployeeData)
  }
}
</script>