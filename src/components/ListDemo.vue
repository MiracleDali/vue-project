<template>
  <div class="example_div" id="列表渲染">
    <h1>v-for: 列表渲染</h1>

    <p class="Explanation">
      我们可以使用 v-for 指令基于一个数组来渲染列表。v-for 指令的值需要使用 item in itmes 形式的特殊语法，
      其中 items 是源数据的数组， 而 item 是迭代选的别名
    </p>
    <p class="Explanation">
      也可以使用 of 作为分隔符来代替 in ,这更接近 JavaScript 的迭代器语法
    </p>
    <p class="Explanation">&lt;div v-for="item of result"&gt;&lt;/div&gt;</p>

    <h3>1、简单使用</h3>
    <p v-for="name in names">{{ name }}</p>

    <h3>2、复杂数据</h3>
    <div v-for="item of result">
      <p>{{ item.id}}</p>
      <p>{{ item.title}}</p>
    </div>

    <h3>3、v-for 支持使用可选的第二个参数表示当前项的位置索引</h3>
    <p v-for="(item, index) of names">{{ item}}-{{index}}</p>

    <h3>4、遍历数组也就是字典</h3>
    <p v-for="(value,key,index) of userInfo">{{ value }}-{{ key }}-{{ index }}</p>

  </div>
</template>


<script>
export default {
  data() {
    return {
      names:['张三', '李四', '王五'],   // 列表数据
      // 列表数据-复杂
      result: [
        {"id": 11, title: '标题1', content: '内容1'},
        {"id": 22, title: '标题2', content: '内容2'},
        {"id": 33, title: '标题3', content: '内容3'}
      ],
      userInfo: {
        name: '张三',
        age: 18,
        sex: '男'
      },
    }
  }
}
</script>