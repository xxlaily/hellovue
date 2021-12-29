<template>
  <div id="app">
    <!--
        如何计算未完成的任务总数：
        将 arr 进行遍历，能够拿到 obj.bol 值；
        通过判断 obj.bol 的真假，就知道当前这条任务是否完成；
        如果完成，不做计算；如果未完成，将其加入到未完成的数量中；
     -->
    <h1>任务列表</h1>
    <p>任务总数：5；还有：4 未完成；【<span class="span1">完成</span>】</p>
    <ul>
      <li>
        <input type="checkbox"  @click.stop='choose(index)'/>
        <span  @click='edit(index)'> </span>
        <input type="text" />
      </li>
    </ul>
    <input type="text" class="add" v-model='msg'/>
    <button @click='add()'>添加</button>
  </div>
</template>

<script>
export default {
  name: "TodoList"
}
</script>

<style scoped>
#app {
  width: 350px;
  margin: 50px auto;
}

li {
  list-style-type: none;
}

ul {
  padding-left: 0;
}

.add {
  width: 200px;
  height: 20px;
  margin-right: 10px;
}

.finish {
  color: #ccc;
  text-decoration: line-through;
}

.span1 {
  color: skyblue;
}
</style>