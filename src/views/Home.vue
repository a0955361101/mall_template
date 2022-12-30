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

const swiperImgs = ref([
  { id: 0, src: 'https://picsum.photos/id/242/1920/500' },
  { id: 1, src: 'https://picsum.photos/id/238/1920/500' },
  { id: 2, src: 'https://picsum.photos/id/249/1920/500' },
  { id: 3, src: 'https://picsum.photos/id/250/1920/500' },
  { id: 4, src: 'https://picsum.photos/id/252/1920/500' },
]);

const productCategory = ref([
  { id: 0, category: 'category1' },
  { id: 1, category: 'category2' },
  { id: 2, category: 'category3' },
  { id: 3, category: 'category4' },
  { id: 4, category: 'category5' },
  { id: 5, category: 'category6' },
  { id: 6, category: 'category7' },
  { id: 7, category: 'category8' },
  { id: 8, category: 'category9' },
]);

const productData = ref([
  { id: 0, name: '品名1', content: '產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述產品敘述', price: 870, img: 'https://picsum.photos/id/666/1920/500' },
  { id: 1, name: '品名2', content: '產品敘述', price: 860, img: 'https://picsum.photos/id/667/1920/500' },
  { id: 2, name: '品名3', content: '產品敘述', price: 850, img: 'https://picsum.photos/id/668/1920/500' },
  { id: 3, name: '品名4', content: '產品敘述', price: 840, img: 'https://picsum.photos/id/669/1920/500' },
  { id: 4, name: '品名5', content: '產品敘述', price: 830, img: 'https://picsum.photos/id/661/1920/500' },
]);

</script>

<template>
  <div class="home">
    <swiper :loop="true" :loopedSlides="7" :spaceBetween="30" :centeredSlides="true" :autoplay="{
  delay: 3000,
  disableOnInteraction: false,
}" :pagination="{
  clickable: true,
}" :navigation="true" :modules="modules" class="mySwiper">
      <swiper-slide v-for="item in swiperImgs" :key="item.id">
        <img :src="item.src" alt="">
      </swiper-slide>
    </swiper>
    <div div class=" home-container">
      <div class="home-sort-list">
        <ul>
          <li v-for="item in productCategory" :key="item.id">
            {{ item.category }}
            <DownArrow />
          </li>
        </ul>
      </div>
      <div class="home-product-list">
        <ProductCrad v-for="item in productData" :key="item.id" :productName="item.name" :productContent="item.content"
          :productPrice="item.price" :productImg="item.img" />
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
