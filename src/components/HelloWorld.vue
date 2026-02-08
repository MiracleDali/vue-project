<template>
  <div class="example_div" id="模板语法" >
    <h1>模板语法</h1>

    <h3>1、模板语法-文本插值</h3>
    <p>{{ msg }}</p>

    <h3>2、模板语法-JavaScript 表达式</h3>
    <p>{{ number + 1 }}</p>
    <p>{{ ok ? 'yes' : 'no' }}</p>
    <p>{{ message.split('').reverse().join('') }}</p>
    <!-- 下面的是不能这样使用的 -->
    <!-- <p>{{ var a =1 }}</p> -->
    <!-- <p>{{ if (ok) { return message } }}</p> -->

    <h3>3、原始HTML</h3>
    <p>{{ rawHtml }}</p>    <!-- 这样是不行的 -->
    <p v-html="rawHtml"></p>
  </div>

  <div class="example_div" id="v-bind:属性绑定">
    <h1>v-bind: 属性绑定</h1>
    <p class="Explanation"> 
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
      // 模板语法
      msg: '神奇的语法',
      number: 10,
      ok: true,
      message: "大家好",
      rawHtml: "<a href='https://www.baidu.com/'>百度一下</a>",
      ///////////////////////////////////////

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
      ///////////////////////////////////////
    }
  }
}
</script>


<style>
/* 每个知识点的外部容器样式 */
.example_div {
  width: auto;
  padding-left: 10px;
  padding-bottom: 10px;
  margin-bottom: 15px;
  border: 1px solid rgba(0, 0, 0, 0.525);
  border-radius: 10px;      /* 圆角 */
  background-color: rgb(226, 234, 251);
}

/* 对于 p 标签 说明文档的样式 */
.Explanation {
  border-left: 5px solid rgb(255, 145, 0);
  padding-left: 10px;
}

/* 属性绑定的样式 */
#bind_id {
  color: rgba(255, 0, 0, 0.801);
}
</style>


