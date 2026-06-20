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
    </div>
</template>


<script setup lang="ts" name="Person123">
    import {ref} from 'vue'

    // 定义数据
    let car = ref({brand: '保时捷', price: 100})
    let games = ref([
        {id:'aysdytfsatr01', name: '地平线'},
        {id:'aysdytfsatr02', name: 'GTA5'},
        {id:'aysdytfsatr03', name: '消消乐'},
    ])
    
    // 定义方法
    function changePrice() {
        car.value.price += 10
    }
    function changeFirstGame() {
        games.value[0]!.name = '模拟器'
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