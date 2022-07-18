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
          menus: [
            
            {
                "id": 1,
                "name": "iki Kişilik Serüven",
                "contents": "6 adet lahmacun + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/sbarro/4lu_lahmacun_menu_477d7a9f43.webp"
            },
            {
                "id": 2,
                "name": "iki Kişilik Acılı Serüven",
                "contents": "6 adet acılı lahmacun + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/sbarro/4lu_lahmacun_menu_477d7a9f43.webp"
            },
            {
                "id": 3,
                "name": "Aile Boyu Lezzet",
                "contents": "10 adet lahmacun + 2.5L içecek",
                "price": 90,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/sbarro/4lu_lahmacun_menu_477d7a9f43.webp"
            },
            {
                "id": 4,
                "name": "Aile Boyu İkiz Lezzet",
                "contents": "5 adet lahmacun + 5 adet acılı lahmacun + 2.5L içecek",
                "price": 90,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/sbarro/4lu_lahmacun_menu_477d7a9f43.webp"
            },
            {
                "id": 5,
                "name": "Kral İkili",
                "contents": "2 adet Karışık Pide + 2 adet Kıymalı Pide + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/usta-pideci/kiymali_pide_menu_9c049cd950.webp"
            },
            {
                "id": 6,
                "name": "Kral İkili 2",
                "contents": "2 adet Karışık Pide + 2 adet Yumurtalı Pide + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/usta-pideci/kusbasili_kasarli_pide_menu_7e2fe9ea69.webp"
            },
            {
                "id": 7,
                "name": "Kral İkili 3",
                "contents": "2 adet Karışık Pide + 2 adet Kaşarlı Pide + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/usta-pideci/usta_karisik_pide_menu_3e86fe9080.webp"
            },
            {
                "id": 8,
                "name": "Kral İkili 4",
                "contents": "2 adet Kıymalı Pide + 2 adet Yumurtalı Pide + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/usta-pideci/patatesli_pide_menu_f12a73de6c.webp"
            },
            {
                "id": 9,
                "name": "Kral İkili 5",
                "contents": "2 adet Kıymalı Pide + 2 adet Kaşarlı Pide + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://d3vkdqr0qjxhag.cloudfront.net/usta-pideci/kiymali_pide_menu_9c049cd950.webp"
            },
            {
                "id": 10,
                "name": "Kral İkili 6",
                "contents": "2 adet Yumurtalı Pide + 2 adet Kaşarlı Pide + 1L içecek",
                "price": 50,
                "quantity": 0,
                "img": "https://www.serifebaci.com/thumb/resimler/urun/-1584351681.69541.png/w600/h600"
            }
      ]
    }
  },
  // mounted() {
  //   fetch('http://localhost:3333/menus')
  //   .then(res => res.json())
  //   .then(data => this.menus = data)
  //   .catch(err => console.log(err.message))
  // },
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