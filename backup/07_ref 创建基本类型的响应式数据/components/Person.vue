<template>
    <div class="person">
        <h2>姓名：{{name}}</h2>
        <h2>年龄：{{age}}</h2>
        <h2>地址：{{address}}</h2>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
    </div>
</template>


<script setup lang="ts" name="Person123">
    // 引入 ref 函数
    import { ref } from 'vue'
    // setup 函数中的 this 是undefined ，不能使用 this.属性
    // 定义数据
    let name = ref('张三')           
    let age = ref(18)                
    let tel = '12345678901'     
    let address = '中国 北京' 

    // 定义方法
    function changeName() {
        name.value = 'lisi'          
        console.log(name.value)      
    }
    function changeAge() {
        age.value += 1
        console.log(age.value)
    }
    function showTel() {
        alert(tel)
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