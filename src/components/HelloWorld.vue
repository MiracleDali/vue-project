<template>
  <div class="属性绑定">
    <h1>属性绑定</h1>
    <p> 
      注：v-bind 指令将元素的 id 与组件的属性保持一致如果绑定的是 null 或者是 undefined, 
      那么该attribute将会从渲染的元素上移除
    </p>
    <h3>1、属性绑定使用 v-bind:</h3>
    <div v-bind:id="bind_id" v-bind:class="bind_class" v-bind:title="bind_title">Example：属性绑定</div>
    <div :id="bind_id" :class="bind_class" :title="bind_title_two">Example：属性绑定简写</div> 
    <h3>2、布尔型 可以动态控制按钮的可点击状态或者其他</h3>
    <button :disabled="bind_button_disabled">按钮1</button>
    <button :disabled="!bind_button_disabled">按钮2</button>
    <h3>3、使用字典的方式绑定多个值</h3>
    <div v-bind="objectOfAttrs">对象语法</div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      // 属性绑定
      bind_class: "active",
      bind_id: "bind_id",
      bind_title: null,
      bind_title_two: "bind_title_two",
      // 属性绑定控制按钮
      bind_button_disabled: false,   // false 启用按钮，true 禁用按钮
      // 使用字典的方式绑定多个值
      objectOfAttrs: {
        class: 'appclass',
        id: 'appid',
      }  
    }
  }
}

</script>


<style>
/* 属性绑定的样式 */
#bind_id {
  color: rgba(255, 0, 0, 0.801);
}
</style>


