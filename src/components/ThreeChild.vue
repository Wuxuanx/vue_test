<template>
  <div>
    <h2>动画</h2>
    <transition name="hello" :appear="true">
        <h1 v-show="show">hello,WTD2!</h1>
    </transition>
    <button @click="show=!show">显示/隐藏</button>
    <transition-group>
        <h1 v-show="show" key="1">hello,WTD1!</h1>
        <h1 v-show="show" key="3">hello,WTD3!</h1>
    </transition-group>
  </div>
</template>

<script>
import 'animate.css'
export default {
    name: 'ThreeChild',
    data () {
        return {
            show: false,
        }
    }
}
</script>

<style>
h1 {
    background: orange;
}
/* transition不写名字name时，是如下写法 */
/* .v-enter-active {
    animation: atguigu 1s;
}
.v-leave-active {
    animation: atguigu 1s reverse;
} */
/* transition写名字时： */
/* .hello-enter-active{
    animation: 1s atguigu;
}
.hello-leave-active{
    animation: 1s atguigu reverse;
} */
.hello-enter-active, .hello-leave-active {
    transition: 1s liner;
}
/* 进入的起点，离开的终点 */
.hello-enter, .hello-leave-to {
    transform: translateX(-100%)
}
/* 进入的终点，离开的起点 */
.hello-enter-to, .hello-leave {
    transform: translateX(0);
}

    @keyframes atguigu {
        from {
            transform: translateX(-100%);
        }
        to {
            transform: translateX(0px);
        }
    }

</style>