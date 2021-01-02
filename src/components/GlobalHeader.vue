<template>
  <nav class="bg-gray-800 h-16 mb-2">
    <div class="max-w-full mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <div class="flex-shrink-0">
            <img
              class="h-8 w-8"
              src="https://tailwindui.com/img/logos/workflow-mark-indigo-500.svg"
              alt="Workflow"
            />
          </div>

          <div>
            <div class="ml-2 flex items-baseline space-x-4">
              <a href="#" class="px-3 text-white text-xl font-medium"
                >者也专栏</a
              >
              <!-- 添加其他按钮 here -->
            </div>
          </div>
        </div>
        <div>
          <div class="ml-4 flex items-center">
            <div v-if="!user.isLogin">
              <a
                href="#"
                class="px-3 py-1.5 hover:bg-white text-white hover:text-black font-medium text-lg rounded-md border border-white"
                >登陆</a
              ><a
                href="#"
                class="ml-3 px-3 py-1.5 hover:bg-white text-white font-medium hover:text-black text-lg rounded-md border border-white"
                >注册</a
              >
            </div>
            <div v-else>
              <a
                href="#"
                class="text-md px-4 py-2 leading-none rounded text-white mt-4 lg:mt-0"
                >{{ user.name }}</a
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";

export interface UserProps {
  isLogin: boolean;
  name?: string;
  id?: number;
}

export default defineComponent({
  name: "GlobalHeader",
  props: {
    user: {
      type: Object as PropType<UserProps>,
      required: true
    }
  }
});
</script>
