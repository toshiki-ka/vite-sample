<script setup lang="ts">
import { ref, Ref } from "vue";

defineProps<{ msg: string }>();

const count = ref(0);
const userId = ref("");
const password = ref("");
const onInputCommon = (event: Event, r: Ref) => {
  const { target } = event;
  if (target instanceof HTMLInputElement) {
    r.value = target.value;
  }
};
const onInputUserId = (event: Event) => {
  onInputCommon(event, userId);
};
const onInputPassword = (event: Event) => {
  onInputCommon(event, password);
};
</script>

<template>
  <div>
    <h1>{{ msg }}</h1>
    <span>User ID</span>
    <input type="text" id="userId" :value="userId" @input="onInputUserId" />
    <br />
    <span>Password</span>
    <input
      type="text"
      id="password"
      :value="password"
      @input="onInputPassword"
    />
    <br />
    <button type="button" id="loginBtn">Login</button>
  </div>
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
