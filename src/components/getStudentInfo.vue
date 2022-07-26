<template>
  <div>
    <button @click="getStudentInfo">获取学生信息</button>
  </div>
</template>

<script>
// import axios from 'axios';

export default {
    name: 'getStudentInfo',
    data () {
        return {
            info: {
                id: '',
                name: '',
                lists: []
            }
        }
    },
    methods: {
        getStudentInfo() {
            // axios.get('http://localhost:8080/1.txt').then(
            // 使用vue-resource请求数据
            this.$http.get('http://localhost:8080/1.txt').then(
                response => {
                    console.log('请求成功了', response.data)
                    // 合并数据结果，使info对象属性不会缺失
                    this.info = {...this.info, ...response.data}
                },
                error => {
                    console.log('请求失败了', error.message)
                }
            )
        }
    }
}
</script>

<style>

</style>