<template>
    <div :style="{width:realWidth,
                  height:realHeight,
                  backgroundColor:backgroundColor}"></div>
    
</template>
<script>
export default {
    name: 'block',
    computed:{
        realWidth: function() {
            return this.width+ 'px';
        },
        realHeight: function() {
            return this.height + 'px'
        }
    },
    props: {
        width: {
            type: Number,
            default: () => 40
        },
        height: {
            type: Number,
            default: () => 15
        },
        backgroundColor: {
            type: String,
            default: () => "white"
        }
    },

    
}
</script>
<style lang="less" scoped>
.cellBlock{
    height: 40px;
    width: 15px;
    box-sizing: content-box;
    border:1px solid #000;
}

</style>