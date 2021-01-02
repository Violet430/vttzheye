<template>
  <div>
    <global-header :user="currentUser"></global-header>
    <column-list :list="list"></column-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ColumnList, { ColumnProps } from "./components/ColumnList.vue";
import GlobalHeader, { UserProps } from "./components/GlobalHeader.vue";
const currentUser: UserProps = {
  isLogin: true,
  name: "小旋风今天上山砍柴啦"
}
const testData: ColumnProps[] = [
  {
    id: 1,
    title: "test1的专栏",
    description: "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制",
    avatar: "https://vue3js.cn/docs/logo.png"
  },
  {
    id: 2,
    title: "test2的专栏",
    description:
      "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制， 为了显示更多的数字， 这个地方需要加上很多子多福婚纱开绿灯撒加快了撒谎觉得就爱上了建立健康",
    avatar: "https://vue3js.cn/docs/logo.png"
  },
  {
    id: 1,
    title: "test1的专栏",
    description: "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制"
  },
  {
    id: 2,
    title: "test2的专栏",
    description: "这是一个专栏，名字是专栏，有一段不短的简介，可以自己来定制",
    avatar: "https://vue3js.cn/docs/logo.png"
  }
];

export default defineComponent({
  name: "App",
  components: {
    ColumnList,
    GlobalHeader
  },
  setup() {
    return {
      list: testData,
      currentUser
    };
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
