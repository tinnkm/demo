<template>
  <div :class="{'horizontal': arrangement === 'horizontal'}">
    <BlockItem
      v-for="item in data"
      :text="item.text"
      :key="item.color"
      :backgroundColor="item.color"
      :width="width"
      :height="height"
      :arrangement="arrangement"
      :textPosition="textPosition"
      :textStyle="textStyle"
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
            type: String,
            default: () => '40'
        },
        height: {
            type: String,
            default: () => '15'
        },
        arrangement: {
            type: String,
            default: () => 'vertical'
        },
        textPosition: {
            type: String,
            default: () => 'right'
        },
        textStyle: {
            type: String,
            default: () => 'start'
        },
    }
}
</script>

<style lang="less" scoped>
.horizontal{
    display: inline-flex;
    flex-direction: row-reverse;
}

</style>