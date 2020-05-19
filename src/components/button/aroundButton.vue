<template>
    <div class="contain">
          <span>数值在</span>
          <div class="btn-wrapper">
                <span v-for="(item,index) in data" :key="item.key" class="btn" :class="{'selected': index === selectedIndex}" @click="selected(index)">{{item.lable}}</span>
          </div>
    </div>
</template>
<script>
export default {
    name: 'arround-button',
    props:{
        data: {
            type: Array,
            default: () => []
        }
    },
    data() {
        return {
            selectedIndex: 0
        }
    },
    methods:{
        selected(index){
            this.selectedIndex = index;
            this.$emit('selected',this.data[index].key)
        }
    }
}
</script>
<style lang="less" scoped>
.contain{
    display: inline-flex;
    margin-left: 20px;
    .btn-wrapper{
        margin-left: 5px;
    }
    .btn{
        display: inline-block;
        font-size: 14px;
        color: black;
        background-color: white;
        border: 1px solid #429feb;
        width: 24px;
        height: 20px;
        text-align: center;
    }
    .selected{
        color: white;
        background-color: #429feb;
        
    }
    
}
</style>