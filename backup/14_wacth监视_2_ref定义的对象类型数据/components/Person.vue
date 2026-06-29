<template>
    <div class="person">
        <h1>情况二 监视 ref 定义的对象类型数据</h1>
        <h2>姓名:{{ preson.name }}</h2>
        <h2>年龄:{{ preson.age }}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="changePreson">修改整个人</button>
    </div>
</template>


<script setup lang="ts" name="Person123">
    import {ref, watch} from "vue"

    // data 数据
    let preson = ref({
        name: "张三",
        age: 18,
    })

    // function 方法
    function changeName() {
        preson.value.name += '~'
    }
    function changeAge() {
        preson.value.age += 1
    }
    function changePreson() {
        preson.value = {
            name: "李四",
            age: 20,
        }
    }

    // watch  监视的是 【ref】定义的对象类型数据， 监视的是对象的地址值
    // 若想监视对象内部属性的变化，需要手动开启深度监视  {deep: true}
    watch(preson, (newVal, oldVal) => {
        console.log('person 值发生变化了', newVal, oldVal)
    }, {deep: true, immediate: true})

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