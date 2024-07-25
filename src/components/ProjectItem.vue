<script setup>
import { ref, onMounted, defineProps, defineEmits } from 'vue';
const count = ref(0);

const selected = ref(1);

let imageArray = ref([
  { id: 1, src: require('../images/test1.jpg') },
  { id: 2, src: require('../images/test2.jpg') },
  { id: 3, src: require('../images/test3.jpg') },
  { id: 4, src: require('../images/test4.jpg') },
  { id: 5, src: require('../images/test5.jpg') },
]);

const props = defineProps({
  // items: {
  //   type: String,
  //   required: false
  // }
  items: String
})

const emits = defineEmits(['test'])


onMounted(() => {
  console.log('[ProjectItem.vue] onMounted')
  console.log('[ProjectItem.vue]', count.value)
  console.log('[ProjectItem.vue]', props.items)
})


const onClikButton = (() => {
  // count.value++
  if (selected.value < imageArray.value.length) {
    selected.value++
  }
})

const onClickArrow = ((direction) => {
  if (direction === 'prev' && selected.value > 1) {
    selected.value--
    return
  }
  if (direction === 'next' && selected.value < imageArray.value.length) {
    selected.value++
    return
  }
})

const onClikEmit = (() => {  
  emits('test', 'test!!!')
})

</script>

<template>
  <div>
    <div>title</div>
    <div class="p-item">
      <div class="imageContainer">
        <div class="images" :style="{ transform: 'translate(-' + (selected - 1) * 300 + 'px, 0px)'}">
          <div v-for="i in imageArray" :key="i.id" class="image" :style="{ 'background-image': 'url(' + i.src + ')' }"></div>
        </div>
        <span class="arrow-left" @click="onClickArrow('prev')"></span>
        <span class="arrow-right" @click="onClickArrow('next')"></span>
      </div>

      <div class="p-des">
        <div>{{ count }}</div>
        <button @click="onClikButton">count up</button>
        <button @click="onClikEmit">emit</button>
      </div>
      <div class="p-check">test check</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.p-item {
  display: flex;
  // background:darksalmon;  
  .p-image {
    // width: 200px;
    // height: 200px;
  }
  .p-des {
    display: flex;
    flex-direction: column;
  }
  .imageContainer {
    overflow: hidden;
    position: relative;
    width: 300px;
    height: 300px;
  }
  .images {
    display: flex;
    transition: 0.6s;
    width: fit-content;
  }
  .image {
    height: 300px;
    width: 300px;
    background-size: cover;
    background-position: center center;
  }
  .arrow-left {
    background: url('../images/arrow_right.png') no-repeat;
    background-size: contain;
    transform: scaleX(-1);
    display: block;
    width: 40px;
    height: 40px;
    position: absolute;
    top: 50%;
    opacity: 0.8;
  }
  .arrow-right {
    background: url('../images/arrow_right.png') no-repeat;
    background-size: contain;
    display: block;
    width: 40px;
    height: 40px;
    position: absolute;
    top: 50%;
    right: 0;
    opacity: 0.8;
  }
}
button {
  width: 100px;
  height: 30px;
}
</style>