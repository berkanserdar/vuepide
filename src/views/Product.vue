<template>
  <div class="product" >
        <h3 class="product__head">MENÜ</h3>
            <div class="product__cards">
              <div 
              v-for="product in products"
              :key="product.id"
              class="card"
              >
                <div class="row g-0">
                  <div class="col-md-4">
                    <img
                      v-bind:src="product.img"
                      class="img-fluid rounded-start product__cards__image"
                      alt="..."
                    />
                  </div>
                  <div class="col-md-8">
                    <div class="card-body">
                      <h5 class="card-title">{{product.name}}</h5>
                      <div class="card-text">
                        <span class="price">{{product.price}} ₺</span>
                            <button 
                            @click="addItemToCart(product)"
                            type="button" class="bttn btn btn-primary">
                              Sepete Ekle
                            </button>
                        </div>
                    </div>
                    
                  </div>
                </div>
              </div>
            </div>
      </div>
</template>


<script>
// @ is an alias to /src

export default {

  data() {
    return {
      carts: [],
      products: [ {
            "id": 1,
            "name": "Acılı Lahmacun",
            "quantity": 0,
            "price": 8,
            "img":"https://www.dayikurekmamak.com/wp-content/uploads/2021/01/Dayi-Kurek-Lahmacun-Mamak-acili-600x300.jpg"
        },
        {
            "id": 2,
            "name": "Lahmacun",
            "quantity": 0,
            "price": 8,
            "img":"https://cdn.yemek.com/mncrop/600/315/uploads/2020/04/lahmacun-yeni-one-cikan.jpg"
        },
        {
            "id": 3,
            "name": "Karışık Pide",
            "quantity": 0,
            "price": 10,
            "img": "https://www.ustapideci.com.tr/cmsfiles/products/usta-karisik-pide-1.png?v=30"
        },
        {
            "id": 4,
            "name": "Kıymalı Pide",
            "quantity": 0,
            "price": 9,
            "img": "https://i.ytimg.com/vi/8k1wnbCcod0/maxresdefault.jpg"
        },
        {
            "id": 5,
            "name": "Yumurtalı Pide",
            "quantity": 0,
            "price": 8,
            "img": "https://i.ytimg.com/vi/3XAfNduLS2c/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDEudzxKh-zjivHuuLGe7h5A-sYsQ"
        },
        {
            "id": 6,
            "name": "Kıymalı ve Yumurtalı Pide",
            "quantity": 0,
            "price": 9,
            "img": "https://i2.milimaj.com/i/milliyet/75/1200x675/5c8dd52345d2a05010dbc3bb.jpg"
        },
        {
            "id": 7,
            "name": "Kaşarlı Pide",
            "quantity": 0,
            "price": 8,
            "img": "https://pidemistanbul.com/wp-content/uploads/2020/09/kasarli-pide.jpg"
        },
        {
            "id": 8,
            "name": "Kıymalı ve Kaşarlı Pide",
            "quantity": 0,
            "price": 9,
            "img": "https://i.nefisyemektarifleri.com/2020/08/14/kiymali-kasarli-pide-tam-8-adet.jpg"
        },
        {
            "id": 9,
            "name": "Yumurtalı ve Kaşarlı Pide",
            "quantity": 0,
            "price": 9,
            "img": "https://www.gelgorgari.com/image/cache/data/urunler/kas-800x800.png"
        },
        {
            "id": 10,
            "name": "Kola",
            "quantity": 0,
            "price": 6,
            "img": "https://i0.wp.com/www.nazar.com.tr/wp-content/uploads/2020/12/coca-cola-1-litre.jpg?fit=700%2C700&ssl=1"
        },
        {
            "id": 11,
            "name": "Fanta",
            "quantity": 0,
            "price": 6,
            "img": "https://i0.wp.com/www.nazar.com.tr/wp-content/uploads/2020/12/fanta-1lt.jpg?fit=700%2C700&ssl=1"
        },
        {
            "id": 12,
            "name": "Ayran",
            "quantity": 0,
            "price": 6,
            "img": "https://reimg-carrefour.mncdn.com/mnresize/600/600/productimage/30131964/30131964_0_MC/8797118234674_1541067138378.jpg"
        },
        {
            "id": 13,
            "name": "Acılı Şalgam",
            "quantity": 0,
            "price": 6,
            "img": "https://www.peynircibaba.com/image/catalog/urunler/8693354005689.jpg"
        },
        {
            "id": 14,
            "name": "Şalgam",
            "quantity": 0,
            "price": 6,
            "img": "https://ayb.akinoncdn.com/products/2021/11/02/78872/37d41519-d2ec-4544-be61-0d9739e3d745_size780x780_quality60_cropCenter.jpg"
        }],
    }
  },
  // mounted() {
  //   fetch('http://localhost:3333/items')
  //   .then(res => res.json())
  //   .then(data => this.items = data)
  //   .catch(err => console.log(err.message))
  // },
  methods: {
    addItemToCart(product){
      this.carts.push(product);
      console.log(this.carts)
    }
  },
  name: 'Home',
  components: {},
}
</script>

<style scoped>
.product {
    align-items: center;
    justify-content: center;
    display: flex;
    flex-direction: column;
}
.product__head {
    text-align: center;
    align-items: center;
    margin-bottom: 50px;
}
.product__cards {
    margin-bottom: 50px;
}


.bttn {
    background-color: #e93578 !important;
}
.product__cards__image {
    width: 200px;
    height: 120px;
}
.card-title {

    margin-bottom: 20px !important;
}

.card {
  max-width: 450px;
  margin-bottom: 50px;
}

.card-text {
    display: flex;
    justify-content: space-between;
}

.card__button {
    display: flex;
    justify-content: flex-end;
    margin-right: 40px;
    margin-top: 30px;
}
</style>