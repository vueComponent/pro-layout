<template>
  <a-config-provider :getPopupContainer="getPopupContainer">
    <router-view />
  </a-config-provider>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  setup() {
    const getPopupContainer = (el: Element, dialogContext: any) => {
      if (dialogContext) {
          return dialogContext.getDialogWrap();
        } else {
          return document.body;
        }
    }
    return {
      getPopupContainer,
    }
  }
});
</script>

<style>
#app {
  height: 100%;
}
</style>
