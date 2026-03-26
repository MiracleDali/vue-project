<template>
    <div class="example_div" id="v-on: 事件处理">
        <h1>v-on: 事件传参</h1>

        <button @click="addCount('hello')">事件传参</button>
        <p>{{ count }}</p>
        

    </div>    
</template>



<script>
export default {
    data() {
        return {
            count: 0
        }
    },

    methods: {
        // event 对象
        addCount(msg){
            console.log(msg)
            this.count++
        }
    }
}

</script>