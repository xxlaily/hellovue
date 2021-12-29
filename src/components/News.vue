<template>
  <table border="1">
    <tr>
      <th>新闻标题</th><th>新闻作者</th><th>时间</th>
    </tr>
    <tr v-for="(item,index) in newsList" :key="index">
      <td>{{item.title}}</td>
      <td>{{item.author}}</td>
      <td>{{item.createDate}}</td>
    </tr>
  </table>
</template>

<script>
import axios from "axios";

export default {
  name: "News",
  data(){
    return{
      newsList:[]
    }
  },
  //钩子函数：文件加载之后就会执行
  mounted() {
    axios.get("/api/news?opr=newsList").then((res)=>{
      //res.data是自带的，至于后面怎么获取，需要根据具体的封装数据来决定
      console.log(res.data.newsList);
      this.newsList = res.data.newsList;
    }
    );
  }
}
</script>

<style scoped>

</style>