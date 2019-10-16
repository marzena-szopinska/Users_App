<template>
  <div class="component">
    <h2>User Details:</h2>
    <div v-if="!user">
      <p>Pick a user to show details</p>
    </div>
    <div v-else>
      <h4>You picked user named {{ user.name}}</h4>
      <p>Age: {{user.age}}</p>
      <p>Hobby: {{user.hobby}}</p>
    </div>
    <button v-bind:disabled="!user" v-on:click="editUser">Send to edit</button>
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
  methods: {
    editUser() {
      userBus.$emit("userToEdit", this.user);
    }
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

:disabled {
  border: 2px solid gray;
}
</style>
