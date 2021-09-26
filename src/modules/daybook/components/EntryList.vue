<template>
  <div class="entry-lis-container">
    <div class="px-2 pt-2">
      <input type="text" class="form-control" placeholder="Buscar entrada" />
    </div>
    <div class="entry-scrollarea">
      <Entry v-for="item in 100" :key="item" />
    </div>
  </div>
</template>

<script>
import { defineAsyncComponent } from "vue";

export default {
  components: {
    Entry: defineAsyncComponent(() => import("./Entry.vue")),
  },
};
</script>

<style lang="scss" scoped>
.entry-lis-container {
  border-right: 1px solid #2c3e50;
  height: calc(100vh - 56px);
}
.entry-scrollarea {
  height: calc(100vh - 110px);
  overflow: scroll;

  &::-webkit-scrollbar {
    -webkit-appearance: none;
  }

  &::-webkit-scrollbar:vertical {
    width: 10px;
  }
  &::-webkit-scrollbar-button {
    display: none;
  }

  &::-webkit-scrollbar:horizontal {
    height: 10px;
  }

  &::-webkit-scrollbar-thumb {
    background-color: #797979;
    border-radius: 20px;
    border: 2px solid #f1f2f3;
  }

  &::-webkit-scrollbar-track {
    border-radius: 10px;
  }
}
</style>