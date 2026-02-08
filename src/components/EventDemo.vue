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

    </div>
</template>

<script>
export default {
    data() {
        return {
            count: 0,
            methods_count: 0
        }
    },

    // 所有的方法或者函数都放在 methods 里面
    methods:{
        // 方法
        addCount() {
            // 使用 this. 访问 data 中的数据
            this.methods_count++
        }
    },    
}
</script>