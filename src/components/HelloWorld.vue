<template>
  <div class="hello">
    <div>id：{{text.id}}</div>
    <div>
      <span>内容：</span>
      <input type="text" v-model="text.content">
    </div>
    <div>
      <span>位置：</span>
      <select name="select" v-model="text.postion">
        <option selected>left</option>
        <option>center</option>
        <option>right</option>
      </select>
    </div>

    <button @click="toJson">输出JSON</button>
    <p>模拟输出json：{{json}}</p>

    <button @click="routeTo">跳转到另一个视图Test</button>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        text: {
          id: 1,
          content: '这是初始内容，',
          postion: 'left'
        },
        json: ''
      }
    },
    created() {
      // 组件生命周期--创建时
      console.log('这个组件创建时触发');
    },
    methods: {
      toJson() {
        this.json = JSON.stringify(this.text)
      },
      routeTo() {
        this.$router.push({path: '/test'})
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
