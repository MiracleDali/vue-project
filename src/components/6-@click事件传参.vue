<template>
    <div class="example_div" id="事件处理">
        <h1> 事件传参</h1>
        <p @click="getNameHandler(item)" v-for="(item,index) of names" :key="index">{{ item }}</p>

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
        // event 对象
        getNameHandler(name){
            alert(name)
        }
    }
}

</script>