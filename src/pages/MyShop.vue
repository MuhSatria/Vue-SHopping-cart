<template>
    <section id="app">
      <h1> Shop </h1>
      <div id="body">
        <div class="col-md-12">
          <div class="row">
          <div class="col-md-6">
            <div class="row">
              <div class="card" v-for="content in barangs" :key="content.id">
                <img class="card-img" v-bind:src="content.image" />
                <h5> {{ content.title }} </h5>
                <p> {{ 'Rp' + ' ' + content.price }} </p>
                <button @click="addToCart(content)"> Add to cart </button>
              </div>
            </div>
          </div>
      <!-- <hr> -->
        <div class="col-md-6 content-right">
        <div>
          <ul class="col-md-12 cart-body">
            <li class="col-md-6 list-cart">Name</li>
            <li class="col-md-3 list-cart">Price</li>
            <li class="col-md-3 list-cart">Action</li>
          </ul>
        </div>
        <div>
          <ul class="col-md-12 cart-body"  v-for="content in contents" :key="content.id">
            <li class="col-md-6 list-cart">{{ content.title }}</li>
            <li class="col-md-3 list-cart">{{ 'Rp.'+' '+content.price }}</li>
            <li class="col-md-3 list-cart"><button @click="removeFromCart(content)">remove</button></li>
          </ul>
        </div>
          <div class="total-bayar">
            <h5>Total Bayar</h5>
            <h6>{{'Rp.'+' '+ total }}</h6>
          </div>
        </div>
        </div>
          </div>
      </div>
    </section>
</template>

<script>

export default {
  data() {
    return {
      barangs : [
        {id: 1, image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2019/3/16/3378841/3378841_476055d3-e9fe-4f62-9242-45a2eecb81a7_700_700.jpg', title: 'Beng beng', price: 2500, qty: 0},
        {id: 2, image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/10/13/4334111/4334111_50a48d17-f71e-4979-9e21-75187dfefa4a_720_720.jpg', title: 'Chocholatos', price: 1500, qty: 0},
        {id: 3, image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2019/3/23/913319/913319_a841ffa1-f54b-43dc-8d23-eae397ceb942_700_700.jpg', title: 'SNICKERSS', price: 5500, qty: 0},
        {id: 4, image: 'https://ecs7.tokopedia.net/img/cache/200-square/product-1/2018/9/23/3611450/3611450_0561430a-4623-4ced-a081-e79ee66a0731_1024_1024.jpg', title: 'Fitbar', price: 4500, qty: 0}
      ],
      contents: [],
      qty: 1
    }
    console.log('data', barangs)
  },

  // computed: {
  //   totalBayar() {
  //     var totalBayar = 0;
  //     for (var i = 0; i < this.contents.length; i++) {
  //       totalBayar += this.contents[i].price;
  //     }
  //     return totalBayar;
  //   }
  // },
  computed: {
    total() {
      return this.contents.reduce((acc, content) => acc + Number
      (content.price), 0);
    }
  },

  methods: {
    addToCart(content) {
     content.qty += 1;
     this.contents.push(content)
     console.log('asdasds', content)
    },

    removeFromCart(content) {
      content.qty -= 1;

      this.contents.splice(this.contents.indexOf(content), 1);
    }

    // removeFromCart(content, i) {
    //   // this.contents = this.contents.slice(0, i-1).concat(contents.slice(i.contents.length))
    //   this.contents = this.contents.filter(content => content.id !== content.id)
    // }
  }
}
</script>

<style lang="scss" scoped>

h1 {
  margin-bottom: 25px;
}

body {
  background: #ccc;
  padding: 10px;
  // display: grid;
  // grid-template-columns: repeat(3, 1fr);
  // flex: 1 1 auto;

  .card {
    display: inline-block;
    padding: 5px;
    background: white;
    text-align: center;
    margin-right: 10px;

    .card-img {
      height: 105px;
      width: auto;
    }

    ul {
      list-style: none;
    }
  }

  .card-cart {
    
    li {
      display: inline-flex;
      margin-right: 20px;
    }
  }


  .cart {
    margin-top: 50px;
    overflow: hidden;
    
    .head {
      width: 100%;
      border-bottom: 1px solid #BFBFBF;
      height: 40px;
      display: block;

      .images {
        display: inline-block;
        line-height: 60px;
        margin: 0;

        .img-cart {
          height: 60px;
          width: auto;
        }
        
      }

      .name {
        display: inline-block;
        // line-height: 40px;
        margin: 0;
      }

      .price {
        display: inline-block;
        // line-height: 40px;
        margin: 0;
      }

      button {
        background: red;
        color: white;
        border-style: none;
        font-size: 12px;
        // padding: 15px 32px;
        text-align: center;
        cursor: pointer;
      }
    }
  }

  .cart-body {
    list-style: none;
    display: inline-flex;
    width: 100%;
    padding: 0;

    .list-cart {
      text-align: left;
      margin-right: 10px;

      button {
        background: red;
        color: white;
        border-style: none;
        font-size: 12px;
        // padding: 15px 32px;
        text-align: center;
        cursor: pointer;
      }
    }
  }

  .total-bayar {
    border: 1px solid;
    margin-top: 25px;
    color: red;
  }

  .foother {
    display: inline-block;
    margin-top: 40px;
    bottom: 0;
    background: #BFBFBF;
    width: 100%;
  }

}
</style>


