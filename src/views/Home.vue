<template>
  <div>
        <div class="greyArea">
            <h2 class="greyArea__welcome">LEZZET DİYARINA HOŞ GELDİNİZ</h2>
        </div>
      <div class="menu" >
        <h3 class="menu__head">AVANTAJLI MENÜLER</h3>
            <div class="menu__cards">
              <div 
              v-for="menu in menus"
              :key="menu.id"
              class="card"
              >
                <div class="row g-0">
                  <div class="col-md-4">
                    <img
                      v-bind:src="menu.img"
                      class="img-fluid rounded-start menu__cards__img"
                      alt="..."
                    />
                  </div>
                  <div class="col-md-8">
                    <div class="card-body">
                      <h5 class="card-title">{{ menu.name }}</h5>
                      <p class="card-text">
                        {{ menu.contents }} <span class="price">{{ menu.price }} ₺</span>
                      </p>
                    </div>
                    <div class="card__button">
                      <button type="button" class="bttn btn btn-primary">
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
      menus: []
    }
  },
  mounted() {
    fetch('http://localhost:3333/menus')
    .then(res => res.json())
    .then(data => this.menus = data)
    .catch(err => console.log(err.message))
  },
  name: 'Home',
  components: {},
}
</script>


<style scoped>

.greyArea {
    background-color: #edf0f4;
    display: flex;
    height: 250px;
    align-items: center;
    text-align: center;
    justify-content: center;
    margin-bottom: 50px;
}
.greyArea .greyArea__welcome {
    font-size: 48px;
    font: bolder;
}
.menu {
    align-items: center;
    justify-content: center;
    display: flex;
    flex-direction: column;
}
.menu__head {
    text-align: center;
    align-items: center;
    margin-bottom: 50px;
}
.menu__cards {
    margin-bottom: 50px;
}
.menu__cards__img {
    width: 240px;
    height: 168px;
    padding: 5px;
}
.bttn {
    background-color: #e93578 !important;
}
.card-title {

    margin-bottom: 20px !important;
}

.card {
  max-width: 750px;
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