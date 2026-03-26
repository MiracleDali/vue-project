<template>
  <div class="example_div" id="key 管理 v-for 的状态">
    <h1>key 管理 v-for 的状态</h1>
    <p class="Explanation">
      Vue默认按照”就地更新”的策略来更新通过v-for渲染的元素列表。当数据项的顺序改变时，
      Vue不会随之移动DOM元素的顺序，而是就地更新每个元素，确保它们在原本指定的索引位置上渲染。
      为了给Vue一个提示，以便它可以跟踪每个节点的标识，从而重用和重新排序现有的元素，
      你需要为每个元素对应的块提供一个唯一的key attribute:
    </p>

    <div v-for="item of result" v-bind:key="item.id">
      <p>{{ item.title }}</p>
      <p>{{ item.content }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      result: [
        {"id": 11, title: '标题1', content: '内容1'},
        {"id": 22, title: '标题2', content: '内容2'},
      ],
    }
  }
}
</script>