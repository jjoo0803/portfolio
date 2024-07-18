<script setup>
import MainHeader from '@/components/MainHeader.vue'
import ProjectList from '@/components/ProjectList.vue'
import Menu1 from '@/components/Menu-1.vue'
import Menu2 from '@/components/Menu-2.vue'

const clickMenuHandler = ((seq) => {
  console.log(seq)
  const el = document.getElementsByClassName(`menu-${seq}`)[0]
  el.scrollIntoView({
    behavior: "smooth",
    block: "start"
  })
})
</script>

<template>
  <div class="home">
    <MainHeader @onClickMenu="clickMenuHandler"></MainHeader>
    <Menu1 class="menu-1"></Menu1>
    <Menu2 class="menu-2"></Menu2>
    <ProjectList class="menu-3"></ProjectList>
  </div>
</template>

<style lang="scss" scoped>
.home {
  padding-top: 55px;
}
.menu-1, .menu-2, .menu-3 {
  scroll-margin: 55px;
}
</style>