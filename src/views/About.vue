
<template>
  <div class="About">
    <div class="container location">
      <div class="location__info">
        <div class="card location__info__adress">
          <div class="card-body">
            <h5 class="card-title">Adres</h5>
            <address class="card-text">Birlik Mahallesi <br>
              1234 Sokak <br>
              No: 45 <br> <br>
              Esenler / İstanbul
            </address>
          </div>
        </div>
        <div class="location__tel">
          <div class="card">
            <div class="card-body">
              <h5 class="card-title">Telefon Numaramız</h5>
              <a href="tel:+01234567890"> 0123 45 78 90</a> <br>
              <a href="tel:+09876543210"> 098 765 43 21</a>
            </div>
          </div>
        </div>
        
      </div>
      <div class="location__map"> 
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d96245.1294078515!2d28.786898057566653!3d41.07641765009138!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x14caafe253f39f9b%3A0x349572fb9a436310!2sEsenler%2F%C4%B0stanbul!5e0!3m2!1str!2str!4v1658058109440!5m2!1str!2str" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      </div>
      
  </div>
<div class="galery__carousel container">
        <carousel >
            <carousel-slide v-for="slide in slides" :key="slide" class="carousel-slider">
                <img :src="slide" :alt="slide">
            </carousel-slide>
        </carousel>
      </div>
  </div>
</template>



<script>
// @ is an alias to /src

import Carousel from '@/components/carousel/Carousel.vue';
import CarouselSlide from '@/components/carousel/CarouselSlide';

export default {
  name: 'About',
  data(){
        return {
            slides: [
                'https://picsum.photos/id/230/600/300',
                'https://picsum.photos/id/231/600/300',
                'https://picsum.photos/id/232/600/300',
                'https://picsum.photos/id/233/600/300',
                'https://picsum.photos/id/234/600/300',
                'https://picsum.photos/id/235/600/300',
                'https://picsum.photos/id/236/600/300',
            ]
        }
    },
  components: {
      Carousel : Carousel,
      CarouselSlide : CarouselSlide,
  }
}
</script>

<style scoped>
.location {
  margin-bottom: 50px;
  display: flex;
  flex-direction: row;
  gap: 20px;
  justify-content: space-evenly;
}
.location__info {
    display: flex;
    width: 18rem;
    gap: 20px;
    flex-direction: column;
}
iframe {
  width: 340px;
  height: 320px;
}



.location__tel{
  width: 18rem;
}
.app {
    display:flex;
    justify-content: center;
}

.galery__carousel {
  display: flex;
  justify-content: center;
}

.carousel {
    position:relative;
    overflow: hidden;
    width:800px;
    height:500px;
    z-index:10;
}

.carousel-slider {
    position:absolute;
    top:0;
    left:0;
    bottom:0;
    right:0;
}
.carousel-slider img {
    width:100%;
    height:100%;
}
</style>