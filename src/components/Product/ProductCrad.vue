<script setup>
import { ref, toRefs } from 'vue';

const props = defineProps({
    productName: {
        type: String,
        default: '',
    },
    productContent: {
        type: String,
        default: '',
    },
    productPrice: {
        type: Number,
        default: null,
    },
    productImg: {
        type: String,
        default: '',
    }
});

const { productName, productContent, productPrice, productImg } = toRefs(props);

</script>

<template>
    <div class="crad">
        <div class="product-image">
            <img :src="productImg" alt="">
        </div>
        <div class="product-content">
            <div>{{ productName }}</div>
            <div>{{ productContent }}</div>
            <div class="product-price">NT$ {{ productPrice }}</div>
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
    height: 75%;

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
    padding: 1rem 5px .5rem;
    font-size: 0.875rem;
    height: 25%;

    & :nth-child(2) {
        margin: 0.625rem 0;
        height: 42px;
        overflow: hidden;
        display: -webkit-box;
        /*限制行數 */
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
        white-space: normal;
    }

    .product-price {
        font-weight: bolder;
    }
}
}
</style>