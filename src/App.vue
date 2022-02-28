<script setup>
import { RouterLink, RouterView } from 'vue-router'
import NavBar from '@/components/NavBar.vue'
import LeftMenu from '@/components/LeftMenu.vue'
import Footer from '@/components/Footer.vue';
</script>

<template>
  <NavBar />

  <transition name="slide-fade">
    <RouterView style="margin-top: 70px" />
  </transition>
  <Footer />
</template>

<style>
@import "@/assets/base.css";

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-active {
  opacity: 0.25;
}

</style>
