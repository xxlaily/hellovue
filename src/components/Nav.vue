<template>
  <div id="app">
    <nav>
      <a v-for="(item,index) in navList" :key="index" :class="{'show':item.active}"
        @click="changeActive(item,index)">{{item.name}}</a>
    </nav>
    <p>选择了 <span>{{checkNav}}</span> </p>
  </div>
</template>

<script>
export default {
  name: "Nav",
  data(){
    return{
      checkNav:"HTML",
      navList:[
        {name:"HTML",active:false},
        {name:"CSS",active:false},
        {name:"JavaScript",active:false},
        {name:"VUE.js",active:false}
      ]
    }
  },
  methods:{
    changeActive(item,index){
      //1点击的选项对应的对象的名称 赋值给 checkNav
      this.checkNav = item.name;
      //2修改 当前点击 的 对象的 active
      for(var i=0;i<this.navList.length;i++){
        //把每一个的 activefalse
        this.navList[i].active = false;
      }
      this.navList[index].active=true;
    }
  }
}
</script>

<style scoped>
* {
  margin: 0;
  padding: 0;
}

#app {
  width: 632px;
  margin: 0 auto;
  text-align: center;
}

nav {
  display: inline-block;
  margin: 60px auto 45px;
  background-color: #64B448;
  box-shadow: 0 1px 1px #ccc;
  border-radius: 2px;
}

nav a {
  display: inline-block;
  padding: 18px 30px;
  color: #fff !important;
  font-weight: bold;
  font-size: 16px;
  text-decoration: none !important;
  line-height: 1;
  background-color: transparent;
  -webkit-transition: background-color 0.25s;
  -moz-transition: background-color 0.25s;
  transition: background-color 0.25s;
  cursor: pointer;
}

span {
  display: inline-block;
  padding: 5px 10px;
  background-color: #64B448;
  border-radius: 2px;
  font-size: 18px;
  color: #fff;
}

.show {
  background-color: #e35885;
}

</style>