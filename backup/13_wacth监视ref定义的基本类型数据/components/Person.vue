<template>
    <div class="person">
        <h1>情况一 监视 ref 定义的基本类型数据</h1>
        <h2>当前求和为{{sum}}</h2>
        <button @click="changeSum">点我 sum 加一</button>
    </div>
</template>


<script setup lang="ts" name="Person123">
    import {ref, watch} from "vue"

    // data 数据
    let sum = ref(0)

    // function 方法
    function changeSum() {
        sum.value += 1
    }

    // 监视 ref 定义的基本类型数据
    // watch(监视对象， 回调函数)
    const stopWatch = watch(sum, (newVal, oldVal, options)=>{
        console.log('sum 发生变化了', newVal, oldVal, options)
        // 停止监听
        if (newVal >= 10) {
            stopWatch()
        }
    })
    console.log("qqqq", stopWatch)

</script>

<style scoped>
    .person {
        background-color: skyblue;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 20px;
    }
    button {
        margin-left: 5px;
    }
    li {
        font-size: 20px;
    }
</style>