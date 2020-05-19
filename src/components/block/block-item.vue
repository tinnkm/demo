<template>
    <div class="block-wrapper" :style="{display:'block',width:realWidth,
                  height:realHeight,
                  backgroundColor:backgroundColor}">
         <span :class="spanStyle"  >{{text}}</span>
    </div>  
    
</template>
<script>
export default {
    name: 'block-item',
    computed:{
        realWidth: function() {
            if(this.arrangement === 'vertical'){
                return this.height ;
            }
            return this.width;
        },
        realHeight: function() {
            if(this.arrangement === 'vertical'){
                return this.width;
            }
            return this.height
        },
        spanStyle: function() {
            return 'block-'+this.arrangement+'-'+this.textPosition+'-'+this.textStyle
        }
    },
    props: {
        width: {
            type: String,
            default: () => '40'
        },
        height: {
            type: String,
            default: () => '15'
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
        textStyle: {
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
   // border-bottom: none;
   margin-top:-1px;
   margin-right: -1px;
    span{
        width: 10px;
        font-size: 14px;
        color: #000;
       text-align: center
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