<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <UploadExcelButton />
  </div>
</template>

<script>
import UploadExcelButton from "./components/UploadExcelButton.vue";

export default {
  name: "App",
  components: {
    UploadExcelButton,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
