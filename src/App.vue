<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    {{logo}}
    <h4 :style = "style">{{products[0]}}</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4>{{products[1]}}</h4>
    <p>70 만원</p>
  </div>
  <div>
    <h4>{{products[2]}}</h4>
    <p>40 만원</p>
  </div>
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      logo : '원룸샵',
      style : 'color : blue',
      products : ['역삼동원룸','낙성대원룸','마포구원룸']
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
  margin-top: 60px;
}
</style>
