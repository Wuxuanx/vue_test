<template>
  <div>
    <h2>姓名： {{name}}</h2>
    <button @click="sendStudentName">向FirstChild传值</button>
  </div>

</template>

<script>
export default {
    name: 'SecondChild',
    data () {
        return {
            name: 'WTD2'
        }
    },
    methods: {
        sendStudentName() {
            this.$bus.$emit('hello', 666)
        }
    }
}
</script>

<style>

</style>