<template>
  <div class="col-xs-12 col-sm-6">
    <li v-on:click="pickUser">Name: {{ userInfo.name }}</li>
  </div>
</template>

<script>
import { userBus } from "../main";

export default {
  props: ["userInfo"],
  methods: {
    pickUser() {
      userBus.$emit("pickedUser", this.userInfo);
    }
  }
};
</script>

<style scoped>
li {
  background-color: peru;
  padding: 1rem;
  border-bottom: 2px solid black;
  margin-bottom: 1rem;
  font-weight: 900;
  cursor: pointer;
}
</style>