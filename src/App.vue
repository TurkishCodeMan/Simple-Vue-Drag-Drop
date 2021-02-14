<template>
  <body>
    <div id="app">
      <Drag></Drag>
      <TableDrag></TableDrag>
    </div>
  </body>
</template>

<script>
import Drag from "./components/Drag.vue";
import TableDrag from "./components/TableDrag.vue"

export default {
  name: "App",
  components: {
    Drag,
    TableDrag
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
