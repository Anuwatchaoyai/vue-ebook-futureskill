<template>
  <div class="container">
    <h1>Please add book</h1>
    <div class="box">
      <my-form></my-form>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import MyForm from "../components/MyForm";
export default {
  name: "AddBook",
  components: {
    MyForm,
  },
};
</script>

<style lang="css" scoped>
.box {
  width: 400px;
  margin: 50px auto;
}
</style>