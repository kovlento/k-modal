<template>
  <div id="app">
    <el-button
      type="text"
      @click="openDialog"
    >点击打开 Dialog</el-button>
    <modal
      ref="modal"
      :titleText="titleText"
      :cancelButtonText="cancelButtonText"
      :confirmButtonText="confirmButtonText"
      @func="getMsgFormSon"
    >
      <div slot="dialogContent">
        <el-form
          ref="form"
          :model="form"
          label-width="80px"
        >
          <el-form-item label="活动名称">
            <el-input v-model="form.name"></el-input>
          </el-form-item>
        </el-form>
      </div>
    </modal>
  </div>
</template>

<script>
import modal from "./components/modal.vue";

export default {
  name: "app",
  components: {
    modal
  },
  data() {
    return {
      form: {
        name: ""
      },
      titleText: "我是标题111",
      cancelButtonText: "嘿嘿1111",
      confirmButtonText: "哈哈1111",
    };
  },
  methods: {
    openDialog() {
      this.$refs.modal.openDialog();
    },
    getMsgFormSon(data){
      if(data){
        //do some thing
      }
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
