<template>
  <div>
        <div class="greyArea">
            <h2 class="greyArea__welcome">LEZZET DİYARINA HOŞ GELDİNİZ</h2>
        </div>
      <div class="menu" >
        <h3 class="menu__head">AVANTAJLI MENÜLER</h3>
            <div class="menu__cards">
              <div class="card">
                <div class="row g-0">
                  <div class="col-md-4">
                    <img
                      src="@/assets/acılıLahmacun.jpg"
                      class="img-fluid rounded-start"
                      alt="..."
                    />
                  </div>
                  <div class="col-md-8">
                    <div class="card-body">
                      <h5 class="card-title">Tek kişilik efsane</h5>
                      <p class="card-text">
                        3 lahmacun + 1 içecek <span class="price">30 ₺</span>
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
  name: 'Home',
  components: {}
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

.bttn {
    background-color: #e93578 !important;
}
.card-title {

    margin-bottom: 20px !important;
}

.card {
  max-width: 750px
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