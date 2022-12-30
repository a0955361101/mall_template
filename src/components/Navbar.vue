<script setup>
import ShoppingCart from '@/components/icons/ShoppingCart.vue';
import BurgerMenu from '@/components/icons/BurgerMenu.vue';
import Search from '@/components/icons/Search.vue';
import Uesr from '@/components/icons/User.vue';
import { ref } from 'vue';

const showBurgerMenu = ref(false);
const logo = ref('logo');
const navbarMenu = ref([
    { id: 0, name: '全部商品', url: '/' },
    { id: 1, name: '最新消息', url: '/' },
    { id: 2, name: '服務條款', url: '/' },
    { id: 3, name: '會員中心', url: '/' },
    { id: 4, name: '關於我們', url: '/about' },
    { id: 5, name: '聯絡我們', url: '/' },
    { id: 6, name: '退換貨及退款須知', url: '/' },
]);

const handleBurgerMenuShow = () => {
    showBurgerMenu.value = !showBurgerMenu.value;
};
</script>

<template>
    <div class="navbar">
        <div class="navbar-container">
            <div class="navbar-logo">
                {{ logo }}
            </div>
            <ul class="navbar-menu">
                <li v-for="item in navbarMenu" :key="item.id">
                    <router-link :to="item.url">
                        {{ item.name }}
                    </router-link>
                </li>
            </ul>
            <div class="navbar-user">
                <Search></Search>
                <Uesr></Uesr>
                <ShoppingCart></ShoppingCart>
                <span class="burger-menu" @click="handleBurgerMenuShow">
                    <BurgerMenu></BurgerMenu>
                </span>
            </div>
        </div>
        <div class="close-burger-menu" :class="showBurgerMenu ? 'open-burger-menu' : ''">
        </div>
        <div :class="showBurgerMenu ? 'backdrop' : ''" @click="handleBurgerMenuShow">

        </div>
    </div>
</template>

<style lang="less" scoped>
@import '@/assets/main.less';

.navbar {
    min-height: 90px;
    background-color: #fff;
    box-shadow: var(--box-shadow);
    position: sticky;
    top: 0;
    z-index: 999;

    .navbar-container {
        display: flex;
        align-items: center;
        margin: 0 13.5%;
        padding: 0 1.25rem;

        .rwd(mobile, {
            padding: 0;
            margin: 0 3%;
        });

    .rwd(pc, {
        justify-content: space-between;
    });

.navbar-logo {
    font-size: 3.75rem;
    line-height: 90px;
}

.navbar-menu {
    display: flex;
    flex: 1;
    flex-wrap: wrap;
    justify-content: center;

    .rwd(pc, {
        display: none;
    });

li {
    margin: 0 0.625rem;
    line-height: 90px;

    a {
        color: var(--text-black);
        text-decoration: none;
    }
}
}

.navbar-user {
    svg {
        width: 24px;
        height: 24px;
        margin-left: .625rem;

    }

    .burger-menu {
        display: none;

        .rwd(pc, {
            display: inline-block;
        });


}
}
}

.close-burger-menu {
    position: fixed;
    z-index: 9999;
    top: 0;
    width: 300px;
    height: 100vh;
    transform: translateX(-300px);
    background-color: #888;
    transition-duration: .3s
}

.open-burger-menu {
    transform: translateX(0);
}

.backdrop {
    background-color: rgba(0, 0, 0, 0.6);
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 9998;
}
}
</style>