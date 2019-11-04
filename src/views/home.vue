<template>
  <div>
    this is home page
    <button @click="btnClick">点击传参</button>
    {{num}}
    <Children :num="num" @child="children" />
  </div>
</template>
<script>
import Children from "./children";
export default {
  components: {
    Children
  },
  data() {
    return {
      num: 1
    };
  },
  created() {
    console.log();
    this.$bus.$on("ziji", obj => {
      console.log(obj);
    });
  },
  methods: {
    btnClick() {
      this.num++;
    },
    children(num) {
      this.num = num;
    }
  }
};
</script>
<style scoped>
</style>
