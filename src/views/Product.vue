<template>
  <div class="product" >
        <h3 class="product__head">MENÜ</h3>
            <div class="product__cards">
              <div 
              v-for="(item, index) in items"
              :key="item.id"
              class="card"
              >
                <div class="row g-0">
                  <div class="col-md-4">
                    <img
                      v-bind:src="item.img"
                      class="img-fluid rounded-start product__cards__image"
                      alt="..."
                    />
                  </div>
                  <div class="col-md-8">
                    <div class="card-body">
                      <h5 class="card-title">{{item.name}}</h5>
                      <div class="card-text">
                        <span class="price">{{item.price}} ₺</span>
                            <button 
                            v-on:click="saveForLater(index)"
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
      items: [],
    }
  },
  mounted() {
    fetch('http://localhost:3333/items')
    .then(res => res.json())
    .then(data => this.items = data)
    .catch(err => console.log(err.message))
  },
  // methods: {
  //   saveForLater(index){
  //     this.items.splice(index, 1);
  //   }
  // },
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