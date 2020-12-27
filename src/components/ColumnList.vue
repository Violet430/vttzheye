<template>
  <div class="grid grid-cols-3 w-3/4 mx-auto gap-10">
    <div
      v-for="column in columnList"
      :key="column.id"
      class="border-2 shadow-md rounded-lg pb-2"
    >
      <img
        :src="column.avatar"
        :alt="column.title"
        class="w-1/4 mx-auto rounded-full"
      />
      <h5 class="font-bold text-xl mb-2">{{ column.title }}</h5>
      <p
        class="text-gray-700 text-base text-left px-2 h-24 mb-0.5 overflow-ellipsis"
      >
        {{ column.description }}
      </p>
      <a
        href="#"
        class="px-2.5 py-1 text-blue-600 blod text-sm rounded-md border border-blue-600"
        >进入专栏
      </a>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from "vue";
export interface ColumnProps {
  id: number;
  title: string;
  avatar?: string;
  description: string;
}
export default defineComponent({
  name: "ColumnList",
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup(props) {
    const columnList = computed(() => {
      return props.list.map(column => {
        if (!column.avatar) {
          column.avatar = require("@/assets/defaultColumn.png");
        }
        return column;
      });
    });
    return {
      columnList
    };
  }
});
</script>
