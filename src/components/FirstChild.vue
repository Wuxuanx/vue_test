<template>
  <div>
      <h1>头部</h1>
      <input placeholder="请输入。。。"/>
      <button @click="sendToFather">向父组件传递数据</button>
  </div>
</template>

<script>
export default {
    name: 'FirstChild',
    data () {
        return {
            name: 'WTD2'
        }
    },
    methods: {
        sendToFather() {
            this.$emit('getFirstChild', this.name)
        }
    }
};
</script>

<style>
</style>