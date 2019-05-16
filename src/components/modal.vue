<template>
  <el-dialog
    :title="titleText"
    :visible.sync="dialogVisible"
    width="30%"
  >
    <slot name="dialogContent">
      <h3>我是默认内容</h3>
    </slot>
    <span
      slot="footer"
      class="dialog-footer"
    >
      <el-button @click="cancel">{{cancelButtonText }}</el-button>
      <el-button
        type="primary"
        @click="submit"
      >{{ confirmButtonText }}</el-button>
    </span>
  </el-dialog>
</template>

<script>
export default {
  props: {
    titleText: {
      type: String,
      default: "标题"
    },
    cancelButtonText: {
      type: String,
      default: "取消"
    },
    confirmButtonText: {
      type: String,
      default: "确认"
    }
  },
  data() {
    return {
      dialogVisible: false
    };
  },
  computed: {},
  created() {},
  mounted() {},
  watch: {},
  methods: {
    openDialog() {
      this.dialogVisible = true;
    },
    cancel() {
      this.dialogVisible = false;
    },
    submit() {
      this.$emit("func", 'true');
    },
    sendMsg() {
      
    }
  },
  components: {}
};
</script>

<style scoped lang="scss">
</style>
