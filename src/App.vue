<template>
  <transition name="fade">
    <DetailModal @closeModal = "modalFlg = 0" :products = 'products' :clickedNum = 'clickedNum' :modalFlg = 'modalFlg'/>
  </transition>
  <div class = "menu">
    <!-- <a v-for="(menu,i) in menuList" :key="i">{{menuList[i]}}</a> -->
    <a v-for="menu in menuList" :key="menu">{{menu}}</a>
    
  </div>

  
  <DiscountCom v-if="showDiscount == true"/>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->

  <button @click="priceSort">가격순정렬</button>
  <button @click="priceSortDown">가격역순정렬</button>
  <button @click="sortBack">되돌리기</button>


  <ItemCard @openModal = "modalFlg = 1;clickedNum = $event" :product = 'product' v-for="product in products" :key="product"/>
</template>

<script>
import data from './assets/data.js';
import DiscountCom from './components/DiscountCom.vue';
import DetailModal from './components/DetailModal.vue';
import ItemCard from './components/ItemCard.vue';



export default {
  name: 'App',
  data() {
    return {
      showDiscount : true,
      clickedNum : 0,
      modalFlg : 0,
      logo : '원룸샵',
      style : 'color : blue',
      products : data,
      nocngProducts : [...data],
      menuList : ['Home','Shop','About'],
      valueList : ['30','40','50'],
      faultCntList : [0,0,0]
    }
  },
  methods: {
    increase(i){
      this.faultCntList[i]++;
    },
    priceSort(){
      this.products.sort(function(a,b){
        return a.price-b.price
      });
    },
    sortBack(){
        this.products = [...this.nocngProducts];
    },
    priceSortDown(){
      this.products.sort(function(a,b){
        return b.price - a.price
      })
    }
  },

  mounted(){
    setTimeout(()=>{
      this.showDiscount = false;
    },2000);
  },
  
  components: {
    DiscountCom : DiscountCom,
    DetailModal : DetailModal,
    ItemCard : ItemCard,
  }
}
</script>

<style>
.fade-enter-from{
  /* opacity : 0; */
  transform : translateY(-1000px);
}
.fade-enter-active{
  transition : all 1s;
}
.fade-enter-to{
  /* opacity: 1; */
  transform : translateY(0px);
}
.fade-leave-from{
  opacity : 1;
}
.fade-leave-active{
  transition : all 1s;
}
.fade-leave-to{
  opacity: 0;
}
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
  width:100%;
  margin-top:20px;
}
.discount{
  background: gray;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>
