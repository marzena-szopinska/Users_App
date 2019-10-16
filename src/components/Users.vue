<template>
  <div class="component">
    <h1>The Users:</h1>
    <div class="holder" v-for="user in users">
      <p>{{user.name}}</p>
      <p>{{user.age}}</p>
      <p>{{user.hobby}}</p>
    </div>

    <ul class="row">
      <user-app v-for="user in users" v-bind:userInfo="user" v-bind:key="user.id"></user-app>
    </ul>
    <div class="row">
      <div class="col-xs-12 col-sm-6">
        <user-detail></user-detail>
      </div>
      <div class="col-xs-12 col-sm-6">
        <user-edit></user-edit>
      </div>
    </div>
  </div>
</template>

<script>
import User from "./User.vue";
import UserDetail from "./UserDetail";
import UserEdit from "./UserEdit";

export default {
  data: function() {
    return {
      users: [
        {
          id: 1,
          name: "Max",
          age: "27",
          hobby: "Fishing"
        },
        {
          id: 2,
          name: "John",
          age: "32",
          hobby: "Video Games"
        },
        {
          id: 3,
          name: "Anna",
          age: "20",
          hobby: "Painting"
        }
      ]
    };
  },
  components: {
    "user-app": User,
    "user-detail": UserDetail,
    "user-edit": UserEdit
  }
};
</script>



<style scoped>
div {
  background-color: lightblue;
}

.holder {
  background-color: yellow;
  padding: 1rem;
  margin: 1rem;
}

ul {
  list-style: none;
}
</style>
