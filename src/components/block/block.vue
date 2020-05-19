<template>
    <div class="block-wrapper" :style="{display:'block',width:realWidth,
                  height:realHeight,
                  backgroundColor:backgroundColor}">
        <span class="block-top-left" >0</span>
    </div>  
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
.block-wrapper{
    position: relative;
    background-color: green;
    width: 200px;
    height: 200px;;
}
.block-top{
    &-left{
        position:absolute;
        transform: translate(-50%,-20px);
    }
    &-center{
        position:absolute;
        left: 50%;
        transform: translate(-50%,-20px);
    }

}

.block-bottom{
    &-left{
        position:absolute;
        bottom: 0;
        transform: translate(-50%,20px);
    }
    &-center{
        position:absolute;
        bottom: 0;
        left: 50%;
        transform: translate(-50%,20px);
    }

}

</style>