<script setup>
import ProductCrad from '@/components/Product/ProductCrad.vue';
import DownArrow from '@/components/icons/DownArrow.vue';
import { Autoplay, Pagination, Navigation } from "swiper";
import { Swiper, SwiperSlide } from 'swiper/vue';
import { ref } from 'vue';
import 'swiper/css';
import "swiper/css/pagination";
import "swiper/css/navigation";

const modules = [Autoplay, Pagination, Navigation];

</script>

<template>
  <div class="home">
    <swiper :loop="true" :loopedSlides="7" :spaceBetween="30" :centeredSlides="true" :autoplay="{
  delay: 3000,
  disableOnInteraction: false,
}" :pagination="{
  clickable: true,
}" :navigation="true" :modules="modules" class="mySwiper">
      <swiper-slide><img src="https://picsum.photos/id/242/1920/500" alt=""></swiper-slide>
      <swiper-slide><img src="https://picsum.photos/id/238/1920/500" alt=""> </swiper-slide>
      <swiper-slide> <img src="https://picsum.photos/id/239/1920/500" alt=""></swiper-slide>
      <swiper-slide> <img src="https://picsum.photos/id/240/1920/500" alt=""></swiper-slide>
      <swiper-slide> <img src="https://picsum.photos/id/241/1920/500" alt=""></swiper-slide>
    </swiper>
    <div div class=" home-container">
      <div class="home-sort-list">
        <ul>
          <li>
            選項1
            <DownArrow />
          </li>
          <li>
            選項2
            <DownArrow />
          </li>
          <li>
            選項3
            <DownArrow />
          </li>
          <li>
            選項4
            <DownArrow />
          </li>
          <li>
            選項5
            <DownArrow />
          </li>
          <li>
            選項6
            <DownArrow />
          </li>
          <li>
            選項7
            <DownArrow />
          </li>
          <li>
            選項8
            <DownArrow />
          </li>
          <li>
            選項9
            <DownArrow />
          </li>
          <li>
            選項10
            <DownArrow />
          </li>
        </ul>
      </div>
      <div class="home-product-list">
        <ProductCrad />
        <ProductCrad />
        <ProductCrad />
        <ProductCrad />
        <ProductCrad />
      </div>
    </div>
  </div>
</template>

<style lang="less" scoped>
@import '@/assets/main.less';

.home {
  background-color: #fff;
  width: 100%;

  .home-container {
    display: flex;
    margin: 0 13.5%;
    padding: 1.25rem 0 1.25rem 0;

    .home-sort-list {
      flex: 1 0 auto;
      padding-left: 1rem;

      .rwd(mobile, {
        display: none;
      });

    ul {
      display: flex;
      flex-direction: column;

      li {
        padding: 0.5rem;
        display: flex;
        align-items: center;
        justify-content: space-between;

        svg {
          width: 24px;
          height: 24px;
        }
      }
    }
  }

  .home-product-list {
    display: flex;
    flex-wrap: wrap;
    flex: 11 0 0;
  }
}
}

:deep(.swiper) {
  .swiper-slide {

    img {
      object-fit: cover;
      object-position: center;
      width: 100%;
    }

  }

  .swiper-pagination {
    .swiper-pagination-bullet {
      background: rgb(255, 255, 255);
    }

    .swiper-pagination-bullet-active {
      background: rgb(255, 255, 255);
    }


  }

  .swiper-button-prev,
  .swiper-button-next {
    color: rgb(255, 255, 255);
    opacity: .7;

    &::after {
      font-size: 1.75rem;
    }
  }
}
</style>
