<template>
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide" v-for="(card, i) in cards" :key="i">
                <cards></cards>
            </div>
        </div>
        <!-- Add Pagination -->
        <div class="swiper-pagination"></div>
        <!-- Add Arrows -->
        <div class="swiper-button-next"></div>
        <div class="swiper-button-prev"></div>
    </div>
</template>

<script>
import Swiper from 'swiper';
import cards from './cards'
  export default {
    data () {
      return {
        cards:[
            {name:1},{name:1},{name:1},{name:1},
            {name:1},{name:1},{name:1},{name:1},{name:1},{name:1},
            {name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},
            {name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},
            {name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},
        ],
      }
    },
    components:{
        cards
    },
    mounted(){
        new Swiper('.swiper-container', {
            slidesPerView: 1,
            loop: false,
            loopFillGroupWithBlank: true,
            pagination: {
                el: '.swiper-pagination',
                clickable: true,
                 dynamicBullets:true,
            },
            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev',
            },
            breakpoints: {
                768: {
                slidesPerView: 2,
                spaceBetween: 40,
                 pagination: {
                    el: null,
                    clickable: true,
                    dynamicBullets:false,
                },
                },
                868: {
                slidesPerView: 4,
                spaceBetween: 40,
                 pagination: {
                    el: null,
                    clickable: true,
                    dynamicBullets:false,
                },
                },
                1400: {
                slidesPerView: 5,
                spaceBetween: 50,
                pagination: {
                    el: null,
                    clickable: true,
                    dynamicBullets:false,
                },
                },
            }
        });
    }
  }
</script>
<style>
    @import "../utils/swiper.min.css";
    .swiper-container {
        width: 100%;
        height: 300px;
    }
    .swiper-button-disabled{
        display: none;
    }
</style>
