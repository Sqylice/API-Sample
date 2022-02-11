<template>
  
</template>

<script>
import axios from 'axios'

export default {
    name: 'EmployeeData',
    data() {
        return{
            Employees: []
        }
    },
    methods: {
        async getEmployeeData() {
            const res = await axios.get('http://dummy.restapiexample.com/api/v1/employees.json')
            console.log(res)
        }
    },
    created() {
        this.getEmployeeData()
    },
    // data: function(){
    //     return{
    //         letters: json.letters
    //     };
    // },
    // mounted: function(){

    // }
}
</script>

<style>

</style>