<script setup>
import { ref } from 'vue';

</script>

<template>
    <div class="crad">
        <div class="product-image">
            <img src="https://picsum.photos/id/666/1920/500" alt="">
        </div>
        <div class="product-content">
            <div>產品名稱測試字數測試字數測試字數測試字數測試字數測試字數</div>
            <div class="product-price">NT890</div>
        </div>
    </div>
</template>

<style lang="less" scoped>
@import '@/assets/main.less';

.crad {
    width: 30%;
    min-height: 400px;
    padding: 0.5rem 0 1rem 0;
    margin: 0 0 .75rem 1.25rem;
    box-shadow: var(--box-shadow);

    .rwd(pc, {
        width: 45%;
    });

.rwd(mobile, {
    width: 100%;
});

.product-image {
    height: 85%;

    img {
        object-fit: cover;
        object-position: center;
        width: 100%;
        height: 100%;
        border-radius: 5px 5px 0 0;

    }
}

.product-content {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem 5px 0;
    font-size: 0.875rem;

    .product-price {
        margin-top: 0.5rem;
        font-weight: bolder;
    }
}
}
</style>