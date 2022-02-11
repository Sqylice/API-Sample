<div v-if="!EmployeeData"></div>
<template  v-else>
    <div>
        <div v-for="Employee in EmployeeData" v-bind:key="Employee.id">
            <div class="card" style="width: 15rem;">
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
//Pull the local .json file and check that it works
    import json from "@/data/employees.json"
    console.log(json.status);

export default {
    data() {
        return {
            // We only care about the data section for our reader
            EmployeeData: json.data
        }
    }
}
</script>

<style>

</style>