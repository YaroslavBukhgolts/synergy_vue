<script setup>
import { RouterLink, RouterView } from 'vue-router'
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <a-layout class="layout">
    <!-- HEADER -->
    <a-layout-header>
      <a-button type="primary" href="/">Home</a-button>
      <a-button type="primary" href="/about">About</a-button>
    </a-layout-header>

    <!-- CONTENT -->
    <a-layout-content style="padding: 0 50px">
      <div :style="{ background: '#fff', padding: '24px', minHeight: '280px' }">Content</div>
      <RouterView />
    </a-layout-content>

    <!-- FOOTER -->
    <a-layout-footer style="text-align: center">
      Ant Design ©2018 Created by Ant UED
    </a-layout-footer>
  </a-layout>
</template>

<style>
  .layout {
    min-height: 100vh;
    width: 100%;
  }
</style>