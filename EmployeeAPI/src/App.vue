<script setup>
// import Navbar from './components/Navbar.vue'
// import Employees from './components/Employees.vue';
import Employees_local from './components/Employees_local.vue';
import Loop from './components/Loop.vue';
</script>

<template>
  <div>
    <header class="wrapper">
        <Navbar />
    </header>
    <body>
      <!-- <Employees /> -->
      <!-- <Employees_local /> -->
      <Loop />
    </body>
  </div>
</template>

<style>
@import './assets/base.css';

</style>
