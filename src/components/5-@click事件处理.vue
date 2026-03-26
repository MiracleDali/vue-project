<template>
    <div class="example_div" id="v-on: 事件处理">
        <h1>v-on: 事件处理</h1>

        <h3>1、内联事件处理器</h3>
        <button v-on:click="count++">Add v-on:click</button>
        <button @click="count++">Add @click</button>
        <p>点击计数：  {{ count }}</p>


        <h3>2、方法事件处理器——常用</h3>
        <button @:click="addCount">调用methods快里面的方法进行处理</button>
        <p>点击计数：  {{ methods_count }}</p>


        <h3>3、事件参数</h3>
        <button @click="addCountEvent">事件传参</button>

        <h3>4、事件传递参数</h3>
        <button @click="transmit('这是传递的参数内容')">事件传递参数</button>

        <h3>5、事件传递参数+event对象传递-点击了谁的名字</h3>
        <p @click="getNameHandler(item, $event)" v-for="(item, index) of names" :key="index">{{ item }}</p>

    </div>
</template>

<script>
export default {
    data() {
        return {
            count: 0,
            methods_count: 0,

            names: ['张三', '李四', '王五']
        }
    },

    // 所有的方法或者函数都放在 methods 里面
    methods:{
        // 方法
        addCount() {
            // 使用 this. 访问 data 中的数据
            this.methods_count++
        },
        
        addCountEvent(e) {
            console.log(e.target.innerHTML)
            e.target.innerHTML = "事件传参" + "  刚刚点击了这个按钮"
        },

        // 事件传参
        transmit(message) {
            alert(message)
        },

        // 获取点击谁的名字
        getNameHandler(name, e){
            alert(name)
            console.log(e)
        }
    },    
}
</script>