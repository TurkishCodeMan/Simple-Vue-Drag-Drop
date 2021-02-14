<template>
  <div class="container mt-3">
    <h2 class="text-center text-primary">Drag & Drop</h2>
    <div class="d-flex justify-content-center align-items-center">
      <div class="col-md-4">
        <div class="p-2 alert alert-secondary">
          <h3>BackLog</h3>

          <draggable
            class="list-group"
            :list="arrLog"
            group="tasks"
            tag="div"
            draggable=".list-group-item"
                :bind="dragOptions"
          >
            <transition-group
              enter-active-class="animated bounce"
              leave-active-class="animated fade"
            >
              <div
                class="list-group-item"
                v-for="element in arrLog"
                :key="element.id"
              >
                {{ element.task }}
              </div>
            </transition-group>
          </draggable>
        </div>
      </div>
      <div class="col-md-4">
        <div class="p-2 alert alert-warning">
          <h3>Test</h3>

          <draggable
            class="list-group"
            :list="arrTest"
            group="tasks"
            draggable=".list-group-item"
            :bind="dragOptions"
          >
            <transition-group
              enter-active-class="animated bounce"
              leave-active-class="animated fade"
            >
              <div
                class="list-group-item"
                v-for="element in arrTest"
                :key="element.id"
              >
                {{ element.task }}
              </div>
            </transition-group>
          </draggable>
        </div>
      </div>
      <div class="col-md-4">
        <div class="p-2 alert alert-success">
          <h3>Done</h3>

          <draggable
            class="list-group"
            :list="arrFinished"
            group="tasks"
            draggable=".list-group-item"
                :bind="dragOptions"
          >
            <div
              class="list-group-item"
              v-for="element in arrFinished"
              :key="element.id"
            >
              {{ element.task }}
            </div>
          </draggable>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";
export default {
  data() {
    return {
      arrLog: [
        { id:1,task: "Film İzle" },
        { id:2,task: "Ödev Yap" },
        { id:3,task: "Uyu" },
        { id:4,task: "Uyan" },
      ],
      arrTest: [],
      arrFinished: [],
      drag: "",
    };
  },
  computed:{
    dragOptions(){
      return {
        animation:0,
        ghostClass:'ghost',
        disabled:false
      }
    }
  },
  components: {
    draggable,
  },
};
</script>

<style scoped>
.list-group {
  min-height: 250px;

}

.ghost {
  opacity: 0.5;
  background: #c8ebfb;
}
</style>