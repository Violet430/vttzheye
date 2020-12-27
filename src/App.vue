<template>
  <div class="w-full">
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ColumnList, { ColumnProps } from "./components/ColumnList.vue";

const testData: ColumnProps[] = [
  {
    id: 1,
    title: "test1的专栏",
    description: "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制",
    avatar: "https://vue3js.cn/docs/logo.png",
  },
  {
    id: 2,
    title: "test2的专栏",
    description: "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制",
    avatar: "https://vue3js.cn/docs/logo.png",
  },
  {
    id: 1,
    title: "test1的专栏",
    description: "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制",
    avatar: "https://vue3js.cn/docs/logo.png",
  },
  {
    id: 2,
    title: "test2的专栏",
    description: "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制",
    avatar: "https://vue3js.cn/docs/logo.png",
  },
];

export default defineComponent({
  name: "App",
  components: {
    ColumnList,
  },
  setup() {
    return {
      list: testData,
    };
  },
});
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
