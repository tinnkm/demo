<template>
    <div class="block-wrapper" :style="{display:'block',width:realWidth,
                  height:realHeight,
                  backgroundColor:backgroundColor}">
        <span :class="textStyle" >0</span>
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
        },
        textStyle: function() {
            return 'block-'+this.arrangement+'-'+this.textPosition+'-'+this.style
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
        },
        arrangement: {
            type: String,
            default: () => 15
        },
        textPosition: {
            type: Number,
            default: () => 15
        },
        style: {
            type: Number,
            default: () => 15
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
.block-horizontal-top{
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

.block-horizontal-bottom{
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

.block-vertical-left{
    &-bottom{
        position:absolute;
        bottom: 0;
        transform: translate(-20px,50%);
    }
    &-center{
        position:absolute;
        bottom: 50%;
        transform: translate(-20px,50%);
    }

}

.block-vertical-right{
    &-bottom{
        position:absolute;
        bottom: 0;
        right: 0;
        transform: translate(20px,50%);
    }
    &-center{
        position:absolute;
        right: 0;
        bottom: 50%;
        transform: translate(20px,50%);
    }

}


</style>