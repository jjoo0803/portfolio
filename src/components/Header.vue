<template>
<div class="header">
  <div class="title">Portfolio</div>
  <div class="tab-container">
    <button>Main</button>
    <button>About Me</button>
    <button>Skills</button>
    <button>Projects</button>
  </div>
</div>
</template>

<script>
export default {
  setup() {
  },
}
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-around;
  position: fixed;
  width: 100vw;
  height: 100px;
  
  .title {
    display: flex;
    
  }
  .tab-container {
    display: flex;
    gap: 50px;
    button {
      cursor: pointer;
      font-size: 20px;
      outline: none;
      background: none;
      border: none;
    }
  }
}
</style>