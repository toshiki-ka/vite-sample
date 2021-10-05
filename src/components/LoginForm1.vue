<script setup lang="ts">
import { ref, Ref } from "vue";

defineProps<{ msg: string }>();
const emit = defineEmits(["login"]);

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
const onClickButton = () => {
  emit("login");
};
</script>

<template>
  <div class="siimple-navbar siimple-navbar--green siimple-navbar--fluid">
    <div class="siimple-navbar-title">LoginForm Sample1</div>
  </div>
  <div class="siimple-content siimple-content--large">
    <label class="siimple-label">User ID </label><br />
    <input
      type="text"
      class="siimple-input siimple-input--fluid"
      id="userId"
      :value="userId"
      @input="onInputUserId"
    />
    <br />
    <label class="siimple-label">Password</label>
    <input
      type="text"
      class="siimple-input siimple-input--fluid"
      id="password"
      :value="password"
      @input="onInputPassword"
    />
    <br />
    <br />
    <br />
    <div class="siimple-field">
      <div
        class="
          siimple-btn siimple-btn--navy siimple-btn--fluid
          siimple--text-bold
        "
        id="loginBtn"
        @click="onClickButton"
      >
        Login
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
