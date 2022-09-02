<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <DownloadExcelButton/>
    <UploadExcelButton />
  </div>
</template>

<script>
import UploadExcelButton from "./components/UploadExcelButton.vue";
import DownloadExcelButton from "./components/DownloadExcelButton.vue";

export default {
  name: "App",
  components: {
    UploadExcelButton, DownloadExcelButton
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
