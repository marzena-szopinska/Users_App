<template>
  <div class="component">
    <h1>The Users:</h1>
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

ul {
  list-style: none;
}
</style>
