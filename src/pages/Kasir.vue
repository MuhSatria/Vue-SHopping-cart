<template>
  <div id="app">
      <h1> {{ name }} </h1>
    <div class="col-md-12 Main_Page d-flex">
      <div class="row">
        <div class="col-md-8 content-left Main_Content">
          <h3> Data Barang </h3>
          <div class="row">
            <b-card class="Card_Barang" v-for="(barang_row, index) in Barang" :key="index" v-bind:href="image">
              <img v-bind:src="barang_row.image"/>
              <h6 v-text="barang_row.title"></h6>
              <p v-text="barang_row.descrip"></p>
              <h6> {{ 'Rp' + barang_row.price }} </h6>
              <button @click="addToCart(item)">Add To Cart</button>
            </b-card>
          </div>
        </div>
        <div class="col-md-4 Cart_Kasir">
          <h3> Cart </h3>
          <div class="row" v-show="showCart">
            <div class="col-md-12 Product_List_Cart" v-show="!verified" >
              {{ items.length + (items.length > 1 || items.length === 0 ? "items" : "item") }}
                <ul class="Title_Cart d-flex" v-show="items.length > 0">
                  <!-- <li>
                    <div>Nama</div>
                    <div></div>
                  </li>
                  <li>
                    <div>Harga</div>
                  </li>
                  <li>
                    <div>Total</div>
                  </li>
                  <li>
                    <div>Action</div>
                  </li> -->
                  <li v-for="item in items" :key="item.id">
                    <p><strong>{{ item.quantity }}</strong> - {{ item.title }} </p>
                  </li>
                </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
 data() {
   return {
     name: 'Toko Saya',
     Barang: [
       {
        id:1,
        title: 'Aqua',
        image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/4/28/2642564/2642564_8fff405b-851f-4196-b943-acae3d697e63_800_800.jpg',
        descrip: 'Minuman yg lumayan sehat',
        price: 5000,
        quantity: 0
      },
      {
        id:2,
        title: 'Aqua',
        image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/4/28/2642564/2642564_8fff405b-851f-4196-b943-acae3d697e63_800_800.jpg',
        descrip: 'Minuman yg lumayan sehat',
        price: 5000,
        quantity: 0
      },
      {
        id:3,
        title: 'Aqua',
        image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/4/28/2642564/2642564_8fff405b-851f-4196-b943-acae3d697e63_800_800.jpg',
        descrip: 'Minuman yg lumayan sehat',
        price: 5000,
        quantity: 0
      },
      {
        id:4,
        title: 'Aqua',
        image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/4/28/2642564/2642564_8fff405b-851f-4196-b943-acae3d697e63_800_800.jpg',
        descrip: 'Minuman yg lumayan sehat',
        price: 5000,
        quantity: 0
      },
      {
        id:5,
        title: 'Aqua',
        image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/4/28/2642564/2642564_8fff405b-851f-4196-b943-acae3d697e63_800_800.jpg',
        descrip: 'Minuman yg lumayan sehat',
        price: 5000,
        quantity: 0
      },
      {
        id:6,
        title: 'Aqua',
        image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/4/28/2642564/2642564_8fff405b-851f-4196-b943-acae3d697e63_800_800.jpg',
        descrip: 'Minuman yg lumayan sehat',
        price: 5000,
        quantity: 0
      },
    ],
    items: [],
    showChart: false,
    verified: false,
    quantity: 1,
   }
 },

 methods: {
   addToCart(item) {
     item.quantity += 1;
     this.items.push(item);
     console.log('data masuk', item)
   }
 }
}
</script>

<style lang="scss" scoped>
@import "../assets/_kasir.scss";


</style>
