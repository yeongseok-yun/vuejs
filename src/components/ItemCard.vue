<template>
  <div>
    <img :src="product.image" class= "room-img">
    <!-- <img @click= "modalFlg=1; clickedNum = i" :src="products[i].image" class= "room-img"> -->
    <h4 @click = "$emit('openModal', product.id)" :style = "style">{{product.title}}</h4>
    <p>{{product.price}}원</p>
  </div>
</template>

<script>
export default {
    name : 'ItemCard',
    props : {
        product : Object
    }
}

</script>

<style>

</style>