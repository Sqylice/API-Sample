<template>
    <div class="row">
        <div v-for="Employee in EmployeeData" v-bind:key="Employee.id">
            <div class="card bg-dark col-sm-3">
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
    import json from "@/data/employees.json"
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