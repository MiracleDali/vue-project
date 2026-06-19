<template>
    <div class="person">
        <h2>姓名：{{name}}</h2>
        <h2>年龄：{{age}}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
        <hr/>
        <h2>{{a}}</h2>
        <button @click="b">test1</button>
    </div>
</template>


<script lang="ts">
    export default {
        name: 'Person',

        data() {
            return {
                a:100,
            }
        },
        methods: {
            b() {
                console.log('b')
            }
        },

        setup() {
            // setup 函数中的 this 是undefined ，不能使用 this.属性
            // 定义数据
            let name = '张三'           // 注意现在的 name 不是响应式的
            let age = 18                // 注意现在的 age 不是响应式的
            let tel = '12345678901'     // 注意现在的 tel 不是响应式的

            // 定义方法
            function changeName() {
                name = 'lisi'           // 注意现在的 name 不是响应式的 页面没有变化
                console.log(name)       // name 其实改了，但不是响应式的
            }
            function changeAge() {
                age += 1
            }
            function showTel() {
                alert(tel)
            }

            // 返回数据和方法
            return {
                name, age,
                changeName, changeAge, showTel
            }

            // setup 函数的返回值也可以是一个函数
            // return () => 'haha'
        },
    }
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
</style>