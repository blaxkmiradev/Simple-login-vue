<template>
  <div class="d-flex justify-content-center align-items-center vh-100 bg-light">
    <LoginForm v-if="!loggedIn" @login-success="loggedIn = true" />
    <Dashboard v-else />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import LoginForm from './components/LoginForm.vue'
import Dashboard from './views/Dashboard.vue'

const loggedIn = ref(false)
</script>
