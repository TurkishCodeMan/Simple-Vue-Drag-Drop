<template>
  <div class="container mt-3 mb-2">
      <h3 class="text-center">Table-Drag-Drop</h3>
    <div class="row">
      <div class="col-6 mx-auto">
        <table class="table tale-striped">
          <thead class="thead-dark">
            <tr>
              <th>Id</th>
              <th>Name</th>
              <th>Age</th>
            </tr>
          </thead>
          <draggable v-model="list" tag="tbody">
            <tr v-for="item in list" :key="item.name">
              <td>{{ item.id }}</td>
              <td>{{ item.name }}</td>
              <td>{{ item.age }}</td>
            </tr>
          </draggable>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";
export default {
  data() {
    return {
      list: [
        {
          id: 1,
          name: "Ahmet",
          age: 35,
        },
        {
          id: 2,
          name: "Mehmet",
          age: 25,
        },
        {
          id: 3,
          name: "Deneme",
          age: "28",
        },
      ],
    };
  },

  components: {
    draggable,
  },
};
</script>

<style>
</style>