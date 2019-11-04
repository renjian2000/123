<template>
  <div>
    {{num}}
    <button @click="childrenClick">点击向父组件传值</button>
  </div>
</template>
<script>
export default {
  props: ["num"],
  methods: {
    childrenClick() {
      // this.$emit("child", this.num);
      this.$bus.$emit("ziji", { a: 1, b: 2 });
    }
  }
};
</script>