<script setup>
import { defineEmits } from 'vue';

const emits = defineEmits(['onClickMenu'])

const onClickMenu = (seq) => {
  console.log('[MainHeader.vue] onClickMenu() seq', seq)
  emits('onClickMenu', seq)
}
</script>

<template>
  <div class="main-header">
    <div class="main-header-contents">
      <div class="main-title">
        title
      </div>
      <div class="main-menu">
        <div @click="onClickMenu(1)">menu1</div>
        <div @click="onClickMenu(2)">menu2</div>
        <div @click="onClickMenu(3)">menu3</div>
        <div @click="onClickMenu(4)">menu4</div>
      </div>
      <div class="menu-btn">
        =
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '../style/mediaquery.scss';
.main-header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  .main-header-contents {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: auto;
    height: 55px;
    background:lavender;
    padding: 0px 80px;
  }
  .main-menu {
    display: flex;
    gap: 30px;
    div {
      &:hover {
        opacity: 0.8;
      }
      &:active {
        opacity: 0.5;
      }
    }
  }
  .menu-btn {
    display: none;
  }
}

@include mobile {
  .main-header {
    .main-menu {
      display: none;
    }
    .menu-btn {
      display: block;
      width: 30px;
      height: 30px;
      background: cadetblue;
    }
  }
}
</style>