<template>
    <div class="block-wrapper" :style="{display:'block',width:realWidth,
                  height:realHeight,
                  backgroundColor:backgroundColor}">
         <span :class="textStyle"  >{{text}}</span>
    </div>  
    
</template>
<script>
export default {
    name: 'block-item',
    computed:{
        realWidth: function() {
            if(this.arrangement === 'vertical'){
                return this.height + 'px';
            }
            return this.width+ 'px';
        },
        realHeight: function() {
            if(this.arrangement === 'vertical'){
                return this.width + 'px';
            }
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
        text: {
            type: String,
            default: () => '0'
        }
    },

    
}
</script>
<style lang="less" scoped>
.block-wrapper{
    position: relative;
    border: 1px solid #000;
    border-bottom: none;
    span{
        font-size: 14px;
        color: #000;
        text-align: left;
    }
}
.block-horizontal-top{
    &-start{
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
    &-start{
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
    &-start{
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
    &-start{
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