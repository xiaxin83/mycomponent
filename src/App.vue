<template>
  <div id="app">
    <XButton @click="getclick()">默认按钮</XButton>
    <XButton type="primary">主要按钮</XButton>
  </div>
</template>

<script>
import XButton from "@/components/Button.vue";
export default {
  name: "App",

  components: {
    XButton,
  },

  methods: {
    getclick() {
      console.log("11");
    },
  },
};
</script>

<style lang="less"></style>
