<template>
<div class="home">
  <div class="main-page">
    <Header></Header>
  </div>
  <div class="introduce">
    <Introduce></Introduce>
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
    height: 100vh;
    background-color: #333333;
    
  }
  .introduce {
    width: 100vw;
    height: 800px;
    background-color: #E1F4F3;;
  }
  .skills {
    width: 100vw;
    height: 500px;
    background-color: #FFFFFF;
  }
  .project {
    position: relative;
    width: 100vw;
    height: 100vh;
    background-color: #706C61;
  }
}
.test {
  // width: 100vw;
  // height: 100vh;
  // background-color: antiquewhite;
}
</style>