<template>
  <div id="app">
    <list />
  </div>
</template>

<script>
import List from "./components/List";

export default {
  data() {
    return {};
  },
  components: {
    List,
  },
};
</script>

<style>
html {
  background-image: linear-gradient(to right bottom, #6157d1, #bf65bf);
  height: 100%;
  background-attachment: fixed;
}

#app {
  max-width: 560px;
  margin: auto;
}
</style>
