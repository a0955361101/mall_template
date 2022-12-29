<script setup>
import { RouterView } from 'vue-router';
import Navbar from '@/components/Navbar.vue';
import Footer from '@/components/Footer.vue';

</script>

<template>
  <Navbar></Navbar>
  <RouterView />
  <Footer></Footer>
  <div class="copyright">Copyright © 2022 Bill.All Rights Reserved.</div>
</template>

<style lang="less" scoped>
.copyright {
  text-align: center;
  line-height: 50px;
  font-size: 0.75rem;
  color: var(--text-black)
}
</style>
