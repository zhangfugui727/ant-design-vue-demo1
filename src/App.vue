<template>
  <DateTest></DateTest>
  <!-- <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Ant Design Vue 3 in CodeSandbox!" />
  <a-button type="primary" @click="open"> go antdv.com </a-button> -->
</template>
<script>
import DateTest from "./components/TreeTest.vue";
export default {
  name: "App",
  setup() {
    return {};
  },
  components: {
    DateTest: DateTest,
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
