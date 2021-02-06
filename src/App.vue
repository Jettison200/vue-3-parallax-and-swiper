<template>
<Header></Header>
<div>
 <parallax speedFactor="0.08">
        <div class="img">
        </div>
      </parallax>
      <p class="s">Have a Nice Day</p>
      </div>
      <div class="x"></div>

      <swiper class="D"
    :slides-per-view="3"
    :pagination="{ clickable: true }"
    :autoplay="{delay: 2000, disableOnInteraction: false}"
    :space-between="50"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  >
    <swiper-slide class="l">Slide 1</swiper-slide>
    <swiper-slide class="l">Slide 2</swiper-slide>
    <swiper-slide class="l">Slide 3</swiper-slide>
     <swiper-slide class="l">Slide 1</swiper-slide>
    <swiper-slide class="l">Slide 2</swiper-slide>
    <swiper-slide class="l">Slide 3</swiper-slide>
     <swiper-slide class="l">Slide 1</swiper-slide>
    <swiper-slide class="l">Slide 2</swiper-slide>
    <swiper-slide class="l">Slide 3</swiper-slide>
    
  </swiper>
    <div class="x"></div>
</template>

<script>
import Header from './components/Header';
import Parallax from './components/Parallax';
   import { Swiper, SwiperSlide } from 'swiper/vue';
   import SwiperCore, { Pagination, Autoplay } from 'swiper';
    import 'swiper/swiper.scss';
      import 'swiper/components/pagination/pagination.scss';
        SwiperCore.use([Pagination, Autoplay]);
export default {
components:{
  Header,
  Parallax,
   Swiper,
   SwiperSlide
   
},
methods: {
      onSwiper(swiper) {
        console.log(swiper)
      },
      onSlideChange() {
        console.log('slide change')
      },
    }
}
</script>

<style>

*{
    padding: 0;
    margin: 0;
}


.img{
  display: block;
  width: 100%;
  height: 100vh;
    overflow: hidden;
    background-image: url("https://cdn.pixabay.com/photo/2020/08/14/15/22/canal-5488271_960_720.jpg");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
}
.x{
  height: 50vh;
}
.D{
  height: 550px;
  display: flex;
  border: 2px solid black;

}
.l{
min-width: 450px;
height: 550px;

}
.s{
  font-size: 40px;
  color: white;
  position: absolute;
  top: 50%;
  left: 40%;
 margin-left: 40px;
 
}

</style>
