<template>
    <!-- Checking for an empty array -->
    <div v-if="EmployeeData.length">

        <!-- Nice presentation text to contextualise the data -->
        <h2>{{EmployeeData.length}} Employees:</h2>

        <!-- for-loop to go through the whole length of the json -->
        <div v-for="Employee in EmployeeData" v-bind:key="Employee.id">
            <div class="card" style="width: 15rem;">
                <!-- As no images are in the file, this isn't strictly necessary but I am keeping it here in case pictures were to be added -->
                <!-- <img class="card-img-top" src="{{ Employee.profile_image }}" alt="A profile picture of the employee"> -->
                <div class="card-body bg-dark">
                    <h5 class="card-title">{{ Employee.employee_name }}</h5>
                    <p class="card-text">Salary: {{ Employee.employee_salary }}</p>
                    <p class="card-text">Age: {{ Employee.employee_age }}</p>
                </div>
            </div>
        </div>
    </div>

    <!-- If no data has been found then we tell the user that the data is being loaded -->
    <div v-else>
        <h4>Loading...</h4>
    </div>
</template>

<script>
//Import axios from files to use the axios functions
import axios from 'axios'

//Pull the local .json file for a cached redundant data copy
import json from "@/data/employees.json"

export default {
    data () {
    return {
        //Default empty array to be overwritten, if this is empty we will have a "loading" text
        EmployeeData: [],
    }
},
mounted () {
    axios
        // get the url in question
        .get('http://dummy.restapiexample.com/api/v1/employees', {timeout:4000})

        // separate the data array that we are interested in
        .then(response => (this.EmployeeData = response.data.data))

        // if we get an error (like 429) then we pull out our redundant cached copy
        // TODO: overwrite the local copy whenever we have a successful get
        .catch(error => (this.EmployeeData = json.data))
    }
}
</script>