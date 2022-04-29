<template>
  <div class="black-bg" v-if="modalFlg == 1">
    <div class = "white-bg">
      <h4>{{products[clickedNum].title}}</h4>
      <p>{{products[clickedNum].content}}</p>
      <img class = "room-img" :src = "products[clickedNum].image">
      <p>{{products[clickedNum].price}}원</p>
      <DiscountCom/>
      <p @click = "$emit('closeModal')">닫기</p>
    </div>
  </div>
</template>

<script>
export default {
    name : 'DetailModal',
    props : {
        products : Array,
        clickedNum : Number,
        modalFlg : Number
    }
}
</script>

<style>

</style>