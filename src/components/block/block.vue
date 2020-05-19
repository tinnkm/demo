<template>
  <div>
    <BlockItem
      v-for="item in data"
      :text="item.text"
      :key="item.color"
      :backgroundColor="item.color"
      :width="width"
      :height="height"
      :arrangement="arrangement"
      :textPosition="textPosition"
      :style="style"
    ></BlockItem>
  </div>
</template>

<script>
import BlockItem from '@/components/block/block-item.vue'
export default {
    components: {BlockItem},
    props:{
        data:{
            type: Array,
            default: () => []
        },
        width: {
            type: Number,
            default: () => 40
        },
        height: {
            type: Number,
            default: () => 15
        },
        arrangement: {
            type: String,
            default: () => 'vertical'
        },
        textPosition: {
            type: String,
            default: () => 'right'
        },
        style: {
            type: String,
            default: () => 'start'
        },
    }
}
</script>