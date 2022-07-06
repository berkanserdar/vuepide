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
    <div class="cart__content">
      <div class="cart__content__items">
        <div class="card cart__card">
          <div class="card-body">
          This is some text within a card body.
          </div>
          <div class="d-grid gap-2 d-md-block cart__buttons">
          <button class="btn btn-primary extButton" type="button">-1</button>
          <button class="btn btn-success addButton" type="button">+1</button>
          </div>
        </div>
          <div class="cart__dell"><i class="fa-solid fa-trash"></i></div>
      </div>
    </div>
    <div class="cart__button mt-3">
    <div class="receipt">
      <button type="button" id="myBtn" class="btn btn-primary">Sipariş ver</button>
    </div>
    </div>
  </div>
</template>


<script>
// @ is an alias to /src

export default {
  name: 'Cart',
  components: {}
}

</script>

<style scoped>
  .cart {
    max-width: 900px;
  }
  .cart__card{
    flex-direction: row !important;
    align-items: center;
    max-width: 80%;
  }
  .form-control {
    height: 100px; 
    width: 200px;
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

  }

</style>