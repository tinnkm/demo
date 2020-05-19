<template>
    <div class="orangeBlock">
        <Block v-for="item in data" 
        :text="item.text" 
        :key="item.color" 
        :backgroundColor="item.color" 
        :width="width"
        :height="height"
        :arrangement="arrangement"
        :textPosition="textPosition"
        :style="style"></Block>
    </div>
</template>
<script>
import Block from '@/components/block/block.vue'
export default {
    components: [Block],
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
<style lang="less" scoped>
.orangeBlock{
    display: inline-block;
    width: 4px;
    height: 16px;
    background: #f18b4c;
}
    
</style>