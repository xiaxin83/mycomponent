<template>
  <button
    @click="handleClick"
    :class="[type ? 'x-button--' + type : '', 'button_init']"
  >
    <span class="font-style">
      <slot></slot>
    </span>
  </button>
</template>

<script>
export default {
  name: "x-button",
  props: {
    type: {
      type: String,
      default: "default",
    },
  },
  data() {
    return {};
  },

  mounted() {
    console.log(this.type);
  },

  methods: {
    handleClick(e) {
      this.$emit("click", e);
    },
  },
};
</script>

<style lang="less" scoped>
// 基础样式开始
.button_init {
  /* 清除默认边框 */
  border: 0;
  outline: none;
  /*清除默认背景 */
  background-color: transparent;
  padding: 12px 20px;

  border: 1px solid #dcdfe6;
  border-radius: 15%;

  cursor: pointer;
  .font-style {
    color: #606266;
    font-size: 10px;
  }
}

// 默认按钮
.x-button--default:hover {
  border: 1px solid #c6e2ff;
  background-color: #ecf5ff;
  .font-style {
    color: #409eff;
    transition: all 0.4s;
  }
  transition: all 0.4s;
}
// 基础样式结束
.x-button--primary {
  border: 1px solid #c6e2ff;
}
// 主要按钮;
</style>
