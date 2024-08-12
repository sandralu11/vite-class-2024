<script setup>
import { ref } from 'vue'
const api = 'https://todolist-api.hexschool.io/'
const singUp = ref({
  email: '',
  password: '',
  nickname: ''
})
const signupButton = async () => {
  try {
    const res = await axios.post(`${api}/users/sign_up`)
  } catch (error) {}
}
</script>å
<template>
  <div class="week2">
    <h1>W2-串接 Todo List API</h1>
    <input type="email" name="mail" placeholder="mail" v-model="singUp.email" />
    <input type="text" name="password" placeholder="password" v-model="singUp.password" />
    <input type="text" name="nickname" placeholder="nickname" v-model="singUp.nickname" />
    <button type="button" @click="signupButton">註冊</button>
  </div>
</template>

<style></style>
