<template>
    <div class="person">
        姓：<input type="text" v-model="firstName"></input> <br>
        名：<input type="text" v-model="lastName"></input> <br><br>
        <button @click="changeFullName">将全名改为Li-si</button> <br><br>
        全名：<span>{{fullName}}</span>
    </div>
</template>


<script setup lang="ts" name="Person123">
    // 计算属性-computed
    import {ref, reactive, computed, toRefs, toRef} from 'vue'
    let firstName = ref('zhang')
    let lastName = ref('san')

    // 计算属性-computed 且是只读的不能修改
    // let fullName = computed(() => {
    //     return firstName.value.slice(0,1).toUpperCase() + firstName.value.slice(1) + '-' + lastName.value
    // })

    // 计算属性-computed 可读可改
    let fullName = computed({
        // get 读
        get() {
            return firstName.value.slice(0,1).toUpperCase() + firstName.value.slice(1) + '-' + lastName.value
        },
        // set 写
        set(val) {
            const [str1 = '', str2 = ''] = val.split('-')
            firstName.value = str1
            lastName.value = str2
        }
    })
    function changeFullName() {
        fullName.value = 'Li-'
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