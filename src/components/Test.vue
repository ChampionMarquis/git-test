<template>
  <div>
    <div>这是test页面</div>
    <button @click="backTo">返回</button>
  </div>
</template>

<script>
  export default {
    name: "test",
    methods: {
      backTo() {
        this.$router.go(-1)
      }
    }
  }
</script>

<style scoped>

</style>
