<template>
  <div class="example_div" id="v-if:条件渲染">
    <h1>v-if: 条件渲染</h1>

    <h3>1、v-if and v-else</h3>
    <p class="Explanation">v-if 指令用于条件性的渲染一块内容。这块内容只会在指令的表达式返回真值时才被渲染</p>
    <p class="Explanation">v-else 指令用于在 v-if 条件不满足时渲染替代内容。 </p>
    <p class="Explanation">v-if 有较高的切换开销</p>
    <div v-if="flag">你能看见我吗 - 为 true 时显示你</div>
    <div v-else>那你还是看看我吧 - 为 false 时显示你</div>

    <h3>2、v-else-if</h3>
    <p class="Explanation">顾名思义，v-else-if 提供的时相应与 v-if 的 else if 区快。它可以连续多次重复使用</p>
    <div v-if="type === 'A'">A</div>
    <div v-else-if="type === 'B'">B</div>
    <div v-else-if="type === 'C'">C</div>
    <div v-else-if="type === 'D'">Not A/B/C</div>

    <h3>3、v-show</h3>
    <p class="Explanation">可以按条件显示一个元素的指令</p>
    <p class="Explanation">v-show 有较高的初始渲染开销</p>
    <div v-shwo="flag">条件为 true 时显示</div>
    
  </div>    
</template>


<script>
export default {
  data() {
    return {
        flag: true,   // 改为false后，v-if将不显示内容 v-else将显示内容
        type: "D",
    }
  }
}
</script>