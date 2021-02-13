<template>
  <body>
    <div id="app">
      <Drag></Drag>
    </div>
  </body>
</template>

<script>
import Drag from "./components/Drag.vue";

export default {
  name: "App",
  components: {
    Drag,
  },
};
</script>

<style >
body {
  padding: 0;
  margin: 0;
  background: rgb(230, 228, 228);
}
</style>
