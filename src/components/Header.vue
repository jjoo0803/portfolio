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
  position: fixed;
  width: 100vw;
  height: 100px;
  background-color:ghostwhite;
  .title {
    display: flex;
    .tab-container {
      button {
        
      }
    }
  }
}
</style>