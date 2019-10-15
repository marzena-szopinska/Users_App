<template>
  <div class="component">
    <h1>The Users:</h1>
    <div class="row">
      <div class="col-xs-12 col-sm-6"></div>
      <div class="col-xs-12 col-sm-6"></div>
    </div>
  </div>
</template>

<script>
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
  }
};
</script>



<style scoped>
div {
  background-color: lightblue;
}
</style>
