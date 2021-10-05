<script setup lang="ts">
import { ref } from "vue";
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import LoginForm1 from "./components/LoginForm1.vue";
import PostLogin from "./components/PostLogin.vue";
const formId = ref("loginForm1");
const onLogin = () => {
  formId.value = "loginForm2";
};
</script>

<template>
  <link
    rel="stylesheet"
    href="https://cdn.jsdelivr.net/npm/siimple@3.3.1/dist/siimple.min.css"
  />
  <LoginForm1
    v-if="formId === 'loginForm1'"
    msg="Login Form"
    @login="onLogin"
  />
  <PostLogin v-else />
</template>

<style>
</style>
