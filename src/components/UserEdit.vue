<template>
  <div class="component">
    <h2>User Edit:</h2>
    <div v-if="!userToEdit">
      <p>No user to edit</p>
    </div>
    <div v-else>
      <h4>The user named {{ userToEdit.name }} can be editted now</h4>
      <input type="text" v-on:input="userToEdit.name = $event.target.value" placeholder="edit name" />
      <p>Name: {{userToEdit.name}}</p>
      <input type="text" v-on:input="userToEdit.age = $event.target.value" placeholder="edit age" />
      <p>Age: {{userToEdit.age}}</p>
      <input
        type="text"
        placeholder="edit hobby"
        v-on:input="userToEdit.hobby = $event.target.value"
      />
      <p>Hobby: {{userToEdit.hobby}}</p>
    </div>
    <button v-bind:disabled="!userToEdit" v-on:click="editUser">Edit</button>
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
  },
  methods: {
    editUser() {
      this.userToEdit.name = "Marzena";
      this.userToEdit.age = 28;
      this.userToEdit.hobby = "Yoga";
    }
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
