<script setup>
import { ref, onMounted, defineProps, defineEmits } from 'vue';
const count = ref(0);

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
});


const onClikButton = (() => {
  count.value++
})

const onClikEmit = (() => {  
  emits('test', 'test!!!')
})

</script>

<template>
  <div class="p-item">
    <div class="p-image">
    </div>
    <div class="p-des">
      <div>{{ count }}</div>
        <button @click="onClikButton">count up</button>
        <button @click="onClikEmit">emit</button>
      </div>
  </div>
</template>

<style lang="scss" scoped>
.p-item {
  display: flex;
  background:darksalmon;  
  .p-image {
    // width: 200px;
    // height: 200px;
  }
  .p-des {
    display: flex;
    flex-direction: column;
  }
}
button {
  width: 100px;
  height: 30px;
}
</style>