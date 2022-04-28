<template>
  <div class = "menu">
    <!-- <a v-for="(menu,i) in menuList" :key="i">{{menuList[i]}}</a> -->
    <a v-for="menu in menuList" :key="menu">{{menu}}</a>
    
  </div>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div v-for="(value,i) in valueList" :key="i">
    <h4 :style = "style">{{products[i]}}</h4>
    <p>{{valueList[i]}} 만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      logo : '원룸샵',
      style : 'color : blue',
      products : ['역삼동원룸','낙성대원룸','마포구원룸'],
      menuList : ['Home','Shop','About'],
      valueList : ['30','40','50']
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
.menu {
  background: darkslateblue;
  padding : 15px;
  border-radius: 5px;
}
.menu a {
  color : white;
  padding: 10px;
}
</style>
