<template>
    <div class="example_div" id="事件处理">
        <h1> 事件传参</h1>
        <!-- 这里的 $event 是event对象 -->
        <p @click="getNameHandler(item, $event)" v-for="(item,index) of names" :key="index">{{ item }}</p>

    </div>    
</template>


<script>
export default {
    data() {
        return {
            names: ['张三', '李四', '王五']
        }
    },

    methods: {
        // 这里的 e 是 event 对象
        getNameHandler(name, e){
            alert(name)
            console.log(e)
        }
    }
}
</script>