<template>
  <div class="col-xs-12 col-sm-6">
    <li>Name: {{userInfo.name}}</li>
  </div>
</template>

<script>
export default {
  props: ["userInfo"]
};
</script>

<style scoped>
li {
  background-color: peru;
  padding: 1rem;
  border-bottom: 2px solid black;
  margin-bottom: 1rem;
}
</style>