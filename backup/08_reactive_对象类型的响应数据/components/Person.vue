<template>
    <div class="person">
        <h2>汽车信息：一辆{{car.brand}}车，价值{{car.price}}万</h2>
        <button @click="changePrice">修改汽车价格</button>
        <hr>
        <h2>游戏列表：</h2>
        <ul>
            <li v-for="g in games" v-bind:key="g.id">{{g.name}}</li>
        </ul>
        <button @click="changeFirstGame">修改第一个游戏的名字</button>
        <hr>
        <h2>test: {{obj.a.b.c}}</h2>
        <button @click="changeTest">test</button>
    </div>
</template>


<script setup lang="ts" name="Person123">
    import {reactive} from 'vue'

    // 定义数据
    let car = reactive({brand: '保时捷', price: 100})
    let games = reactive([
        {id:'aysdytfsatr01', name: '地平线'},
        {id:'aysdytfsatr02', name: 'GTA5'},
        {id:'aysdytfsatr03', name: '消消乐'},
    ])
    let obj = reactive({
        a: {
            b: {
                c: 100
            }
        }
    })
    

    // 定义方法
    function changePrice() {
        car.price += 10
    }
    function changeFirstGame() {
        games[0]!.name = '模拟器'
    }
    function changeTest() {
        obj.a.b.c += 10
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
    li {
        font-size: 20px;
    }
</style>