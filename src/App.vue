<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <app-users></app-users>
      </div>
    </div>
  </div>
</template>

<script>
import Users from "./components/Users.vue";
export default {
  components: {
    "app-users": Users
  }
};
</script>

<style>
div.component {
  border: 1px solid black;
  padding: 30px;
}
</style>
