<template>
  <div class="component">
    <h2>User Details:</h2>
    <div v-if="!user">
      <p>Pick a user to show details</p>
    </div>
    <div v-else>
      <p>User Name: {{user.name}}</p>
      <p>User Age: {{user.age}}</p>
      <p>User Hobby: {{user.hobby}}</p>
    </div>
  </div>
</template>

<script>
import { userBus } from "../main";

export default {
  data: function() {
    return {
      user: null
    };
  },
  created() {
    userBus.$on("pickedUser", user => {
      this.user = user;
    });
  }
};
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
