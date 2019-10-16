<template>
  <div class="component">
    <h2>User Edit:</h2>
    <div v-if="!userToEdit">
      <p>No user to edit</p>
    </div>
    <div v-else>
      <h4>The user named {{ userToEdit.name }} can be editted now</h4>
      <p>Name: {{userToEdit.name}}</p>
      <p>Age: {{userToEdit.age}}</p>
      <p>Hobby: {{userToEdit.hobby}}</p>
    </div>
    <button v-bind:disabled="!userToEdit">Edit</button>
  </div>
</template>

<script>
import { userBus } from "../main";

export default {
  data: function() {
    return {
      userToEdit: null
    };
  },
  created() {
    userBus.$on("userToEdit", user => {
      this.userToEdit = user;
    });
  }
};
</script>

<style scoped>
div {
  background-color: lightgreen;
}

:disabled {
  border: 2px solid gray;
}
</style>
