<template>

  <div class="black-bg" v-if="modalFlg == 1">
    <div class = "white-bg">
      <h4>상세페이지</h4>
      <p>상세 내용</p>
      <p @click = "modalFlg = 0">닫기</p>
    </div>
  </div>

  <div class = "menu">
    <!-- <a v-for="(menu,i) in menuList" :key="i">{{menuList[i]}}</a> -->
    <a v-for="menu in menuList" :key="menu">{{menu}}</a>
    
  </div>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div v-for="(value,i) in valueList" :key="i">
    <img @click= "modalFlg=1" :src="products[i].image" class= "room-img">
    <h4 :style = "style">{{products[i].title}}</h4>
    <p>{{products[i].price}} 만원</p>
    <!-- <button @click="increase(i)">허위매물신고</button><span>신고수 : {{faultCntList[i]}}</span> -->
    <!-- <button @mouseover="faultCnt++">허위매물신고</button><span>신고수 : {{faultCnt}}</span> -->
  </div>
</template>

<script>
import data from './assets/data.js'

export default {
  name: 'App',
  data() {
    return {
      modalFlg : 0,
      logo : '원룸샵',
      style : 'color : blue',
      products : data,
      menuList : ['Home','Shop','About'],
      valueList : ['30','40','50'],
      faultCntList : [0,0,0]
    }
  },
  methods: {
    increase(i){
      this.faultCntList[i]++;
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
body{
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg{
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
.menu {
  background: darkslateblue;
  padding : 15px;
  border-radius: 5px;
}
.menu a {
  color : white;
  padding: 10px;
}
.room-img{
  width:150px;
  margin-top:20px;
}
</style>
