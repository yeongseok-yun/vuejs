<template>
  <div class="black-bg" v-if="modalFlg == 1">
    <div class = "white-bg">
      <img class = "room-img" :src = "products[clickedNum].image">
      <h4>{{products[clickedNum].title}}</h4>
      <p>{{products[clickedNum].content}}</p>
      <!-- <input @input = "months = $event.target.value"> -->
      <input v-model="months">
      <p>{{months}}개월 선택함</p><p>{{months * products[clickedNum].price}}원</p>
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
    },
    data() {
      return {
        months: 1,
      };
    },
    watch : {
      months(param){
        if(param > 12){
          this.months = 1;
          alert('12개월 이상 입력 불가')
          
        }
        if(isNan(param) == true){
          this.months = 1;
          alert('문자 입력 불가')
        }
      }
    }
}
</script>

<style>

</style>