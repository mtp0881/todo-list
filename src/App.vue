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
#app {
  position: absolute;
  width: 600px;
  top: 40px;
  left: 50%;
  transform: translateX(-50%);
  z-index: 50;
  background-color: rgba(128, 128, 128, 0.418);
  padding: 30px;
  border-radius: 10px;
}
</style>
