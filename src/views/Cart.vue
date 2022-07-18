<template>
  <div class="cart container">
    <div class="cart__adress">
      <div class="guest__address ">
        <h5 class="card-title">Adres</h5>
        <div class="addAdress mt-4">
          <div class="form-floating">
            <textarea class="form-control" placeholder="Leave a comment here" id="floatingTextarea2"></textarea>
            <label for="floatingTextarea2">Adres</label>
          </div>
          <button type="button" class="btn btn-primary mt-2">Ekle</button>
        </div>
      </div>
    </div>
    <div 
    v-for="(cart, index) in carts"
    :key="cart.id"
    class="cart__content">
      <div class="cart__content__items">
        <div class="card cart__card">
          <div class="card-body">
            <div class="cart__name">{{cart.name}}</div>
            <div class="cart__quantity">
              {{cart.quantity}} Adet
            </div>
            <div class="cart__price">
              {{cart.price}} ₺
            </div>
          </div>
          <div class="d-grid gap-2 d-md-block cart__buttons">
          <button
          @click="updateCart(cart, 'subtract')"
           class="btn btn-primary extButton" type="button">-1</button>
          <button 
          @click="updateCart(cart, 'add')"
          class="btn btn-success addButton" type="button">+1</button>
          </div>
        </div>
          <button
          v-on:click="removeFromCart(index)"
           class="cart__dell"><i class="fa-solid fa-trash"></i></button>
      </div>
      
    </div>

    <div class="total__price">
      <p>
        Toplam Fiyat : 
        <span 
        v-if="carts.length"
        >{{totalTax()}}</span>
      </p>
    </div>
    
    <div>
    <b-button class="cart__siparis" v-b-modal.modal-1>Sipariş ver</b-button>

    <b-modal id="modal-1" title="Sparişiniz verilmiştir">
      <div 
      v-for="cart in carts"
      :key="cart.id"
      class="my-4">
        <p>
          {{cart.quantity}} adet {{cart.name}}
        </p>
        
      </div>
      <p>
        Toplam Fiyat : 
        <span 
        v-if="carts.length"
        >{{totalTax()}}</span>
      </p>
    </b-modal>
  </div>
  </div>
</template>


<script>
// @ is an alias to /src

export default {
  data() {
    return {
      carts: [
        {
            "id": 1,
            "name": "lahmacun",
            "price": 8,
            "quantity": 3
        },
        {
            "id": 2,
            "name": "acılı lahmacun",
            "price": 9,
            "quantity": 3
        }
        ],
    }
  },
  // mounted() {
  //   fetch('http://localhost:3333/carts')
  //   .then(res => res.json())
  //   .then(data => this.carts = data)
  //   .catch(err => console.log(err.message))
  // },
  methods: {
    removeFromCart(index){
      this.carts.splice(index, 1);
    },
  totalTax(){
    return this.carts.reduce((a, b) =>a + b.quantity * b.price, 0)
  },
    updateCart(carts, updateType, index) {
      for(let i = 0; i < this.carts.length; i++ ) {
        if( this.carts[i].id === carts.id){
          if(updateType === 'subtract'){
            if(this.carts[i].quantity !== 1){
              this.carts[i].quantity --;
            } else if(this.carts[i].quantity <= 1) {
              this.carts.splice(index, 1);
            }
          } else {
            this.carts[i].quantity++;
          }
          break;
          }
        }
    }
  },
  name: 'Cart',
  components: {}
}

</script>

<style lang="scss" scoped>
  .cart {
    max-width: 900px;
  }
  .cart__card{
    flex-direction: row !important;
    align-items: center;
    width: 80%;
  }
  .form-control {
    height: 100px; 
    width: 200px;
  }
  .cart__adress{
    margin-bottom: 30px;
  }
  .cart__buttons{
    margin-right: 10px;
  }

  .extButton {
    background: #0d6efd !important;
  }
  .addButton{
    background: #198754 !important;
  }
  .cart__content__items {
    display: flex;
    margin-bottom: 30px;
  }
  .cart__dell{
    border: none;
    background: #fff;
    height: 20px;
    margin-left: 10px;
    display: flex;
    align-self: center;

      i{
        color:red;
      }
  }

  .total__price {
    border: groove;
    border-radius: 10px;
    box-shadow: 5px 5px lightblue;
    width: 300px;
    margin-top: 20px;
    margin-bottom: 20px;

      p {
        padding: 10px;
        text-align: start;
      }
  }

  .cart__siparis {
    background: #e93578;
  }

</style>