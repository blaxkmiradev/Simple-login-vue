<template>
  <div class="card p-4 shadow" style="width: 350px;">
    <h3 class="mb-3 text-center">Login</h3>

    <div class="mb-3">
      <input v-model="email" type="email" class="form-control" placeholder="Email" />
    </div>

    <div class="mb-3">
      <input v-model="password" type="password" class="form-control" placeholder="Password" />
    </div>

    <button @click="login" class="btn btn-primary w-100">Login</button>

    <div v-if="message" class="mt-3 text-center">
      <span :class="{'text-success': success, 'text-danger': !success}">{{ message }}</span>
    </div>
  </div>
</template>

<script setup>
import { ref, defineEmits } from 'vue'

const email = ref('')
const password = ref('')
const message = ref('')
const success = ref(false)

const emit = defineEmits(['login-success'])

const login = () => {
  if (email.value === 'admin@gmail.com' && password.value === '123456') {
    message.value = 'Login success ✅'
    success.value = true
    setTimeout(() => emit('login-success'), 500)
  } else {
    message.value = 'Login failed ❌'
    success.value = false
  }
}
</script>
