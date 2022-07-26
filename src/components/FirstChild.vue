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
    },
    mounted() {
        this.$bus.$off('hello') // 绑定事件前，先解绑该事件，以免事件多次绑定，执行多次方法
        this.$bus.$on('hello', (data) => {
            console.log('接收SecondChild的传值：' + data)
        })
    },
    beforeDestroy() {
        this.$bus.$off('hello')
    }
};
</script>

<style>
</style>