<script setup>
import ProjectItemVue from '@/components/ProjectItem.vue'

const testHandler = ((value) => {
  console.log('[ProjectList.vue] testHandler', value)
})

</script>

<template>
  <div class="grid-box">
    <!-- <div class="grid-container">
      <ProjectItemVue 
        v-for="(i, index) in 6"
        :key="index"
        :items="'test'"
        @test="testHandler"
      />
    </div> -->
    <div>
      <ProjectItemVue @test="testHandler"></ProjectItemVue>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '../style/mediaquery.scss';
.grid-box {
  display: flex;
  align-items: center;
  justify-content: center;
}
.grid-container {
  display: grid;
  grid-gap: 30px;
  @include mobile {
    grid-template-columns: repeat(1, 350px);
    grid-auto-rows: 350px;
  }
  @include tablet-v {
    grid-template-columns: 350px 350px;
    grid-template-rows: 350px 350px;
  }
  @include tablet-h {
    grid-template-columns: 350px 350px;
    grid-template-rows: 350px 350px;
  }
  @include desktop {
    grid-template-columns: 350px 350px 350px;
    grid-template-rows: 350px 350px 350px;
  }
}
</style>