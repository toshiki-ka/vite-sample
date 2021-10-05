<script setup lang="ts">
import { ref, Ref } from "vue";

defineProps<{ msg: string }>();
const emit = defineEmits(["login"]);

const userId = ref("");
const password = ref("");
import loginImage from "../../public/login.png";

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
    <div class="siimple-grid">
      <div class="siimple-grid-row">
        <div class="siimple-grid-col siimple-grid-col--10">
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
        </div>
        <div class="siimple-grid-col siimple-grid-col--2">
          <div class="siimple-field">
            <img
              :src="loginImage"
              width="150"
              height="150"
              id="loginBtn"
              @click="onClickButton"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
</style>
