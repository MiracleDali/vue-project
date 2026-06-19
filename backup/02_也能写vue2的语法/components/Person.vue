<template>
    <div class="person">
        <h2>姓名：{{name}}</h2>
        <h2>年龄：{{age}}</h2>
        <button @click="ChangeName">修改名字</button>
        <button @click="ChangeAge">修改年龄</button>
        <button @click="showTel">查看联系方式</button>
    </div>
</template>


<script lang="ts">
    export default {
        name: 'Person',
        
        data() {
            return {
                name: '张三',
                age: 18,
                tel: '12345678901'
            }
        },

        methods: {
            showTel() {
                alert(this.tel)
            },
            ChangeName() {
                this.name = 'lishi_01'
            },
            ChangeAge() {
                this.age += 1
            },
        }
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