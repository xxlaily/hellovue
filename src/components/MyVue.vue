<template>
  <h3>第一个VUE页面</h3>
  <h3>{{msg}}</h3> <!-- 双大括号可以 获取插值表达式的值-->
  <h3>{{obj.name}},{{obj.password}}</h3>
  <h3>{{objs[0].name}}</h3>
<!--  <div id="red" v-if="seen"></div>-->
<!--  <div v-else-if="seen1" ></div>-->
<!--  <span v-else>seen的值是false的时候，我显示出来...</span>-->
  <div id="red" v-show="seen"></div>
<!--  <input type="button" v-on:click="changeSeen" value="点 击"/>-->
  <input type="button" @click="changeSeen" value="点 击"/> <br>
  <input type="text" name="content" v-model='msg' > <br>

  <div v-if="seen" :class="[classA]">毅哥是SuperBoy</div>
  <div v-else :class="[classB]">毅哥是SuperBoy</div>
  <img :src="produceList[0].imgSrc" width="100" height="100"/>
  <ul>
    <li v-for="(item,index) in produceList" :key="index">
        {{index}} --> {{item.name}} --> {{item.price}}
    </li>
  </ul>
</template>

<script>
export default {
  name: "MyVue",
  data(){
    return { //变量或者数据
      msg: "插值表达式1111",
      obj:{id:1,name:"张三",password:"123456"},
      objs:[{id:1,name:"张三",password:"123456"},{id:1,name:"张三",password:"123456"}],
      seen:false,
      classA:"classA",
      classB:"classB",
      produceList:[{name:"菠萝",price:"19.4",imgSrc:"/img/logo.82b9c7a5.png"},
        {name:"苹果",price:"5.6",imgSrc:"/img/logo.82b9c7a5.png"},
        {name:"草莓",price:"9.4",imgSrc:"/img/logo.82b9c7a5.png"},
        {name:"毅哥",price:"250",imgSrc:"/img/logo.82b9c7a5.png"}
      ]
    }
  },
  methods:{
    changeSeen(){
      if(this.seen == true){
        this.seen = false;
      }else{
        this.seen = true;
      }
    }
  }
}
</script>

<style scoped>
  #red{
    width: 100px;
    height: 100px;
    background-color: red;
  }
  .classA{
    width: 100px;
    height: 100px;
    background-color:lavender;
  }
  .classB{
    font-size: 20px;
    color: red;
  }
</style>