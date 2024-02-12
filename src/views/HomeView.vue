<template>
<div class="home">
  <div class="main-page">
    <Header></Header>
    <div class="introduce">
      <Introduce></Introduce>
    </div>
  </div>
  <div class="skills">
    <Skills></Skills>
  </div>
  <div class="project">
    <Project></Project>
  </div>
</div>
</template>

<script>
// @ is an alias to /src
import Header from '@/components/Header.vue'
import Introduce from '@/components/Introduce.vue'
import Skills from '@/components/Skills.vue'
import Project from '@/components/Project.vue'

export default {
  name: 'HomeView',
  components: {
    Header,
    Introduce,
    Skills,
    Project
  }
}
</script>

<style lang="scss" scoped>
.home {
  .main-page {
    width: 100vw;
    height: 700px;
    .introduce {
      background-color: #79B4B7;
    }
  }
  .skills {  
    background-color: #FEFBF3;
  }
  .project {
    background-color: #F8F0DF;
  }
}
.test {
  // width: 100vw;
  // height: 100vh;
  // background-color: antiquewhite;
}
</style>