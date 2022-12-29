<script setup>
import ShoppingCart from '@/components/icons/ShoppingCart.vue';
import BurgerMenu from '@/components/icons/BurgerMenu.vue';
import Search from '@/components/icons/Search.vue';
import Uesr from '@/components/icons/User.vue';

</script>

<template>
    <div class="navbar">
        <div class="navbar-container">
            <div class="navbar-logo">
                logo
            </div>
            <ul class="navbar-menu">
                <li>分類001</li>
                <li>分類002</li>
                <li>分類003</li>
                <li>分類004</li>
                <li>分類005</li>
                <li>分類006</li>
                <li>分類007</li>
            </ul>
            <div class="navbar-user">
                <Search></Search>
                <Uesr></Uesr>
                <ShoppingCart></ShoppingCart>
                <span class="burger-menu">
                    <BurgerMenu></BurgerMenu>
                </span>
            </div>
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
}
</style>