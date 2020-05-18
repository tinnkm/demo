<template >
    <div class="setPanel">
      <div class="title">
        <div class="colorSet">色谱设置</div>
      </div>
      <div class="content">
        <div class="numberModal">
          <orangeBlock></orangeBlock>
          <span class="numberStyle">数值样式</span>
          <span class="ruler">卡尺式</span>
          <span class="mediate">居中式</span>
        </div>
        <dotted></dotted>
        <div class="arrangeModal">
          <div class="top">
             <orangeBlock></orangeBlock>
             <span class="arrangeStyle">排列样式</span>
          </div>
          <div class="bottom">
            <div class="upright">
              <span class="upright-text">竖排</span>
            </div>
            <div class="across">
              <span class="across-text">横排</span>
            </div>
          </div>
        </div>
         <dotted></dotted>
        <div class="onePiece">
          <div class="top">
             <orangeBlock></orangeBlock>
             <span class="descript">单色块的长宽</span>
          </div>
          <div class="bottom">
            <span class="left" >长</span>
            <input v-model="width" type="text" style="width:35px,border:0.5px solid #bebcbc">
            <span class="right">宽</span>
            <input v-model="height" type="text" style="width:35px,border:0.5px solid #bebcbc">
          </div>
          <div></div>
        </div>
      </div>
      <block :width="width" :height="height" backgroundColor="red"></block>
   </div>
</template>

<script>
import orangeBlock from "@/components/orangeBlock/orangeBlock.vue"
import block from "@/components/block/block.vue"
import dotted from '@/components/dotted/dotted.vue'
export default {
  components:{
    orangeBlock,
    dotted,
    block
  },
  data () {
    return {
      width: '',
      height: ''
    }
  }

}
</script>
<style lang="less" scoped>
  .setPanel{
     width: 265px;
     height: 220px;
     background: #f8feff;
     margin-top: 20px;
     margin-left: 20px;
     box-shadow: #cdcdcd 0px 0px 50px 10px ;
     .title{
       background: #e3f1f5;
       .colorSet{
         background: #429feb;
         color: #fff;
         font-size:12px;
         width: 70px;
         height: 32px;
         line-height: 32px;
         text-align: center;
       }
     }
     .content{

      padding: 0 12px;
     
      .numberModal{
       height: 32px;
       width: 100%;
       padding-left: 4px;
       padding-top: 10px;
       orangeBlock{
         vertical-align:top;
       }
       .numberStyle{
         font-size:14px;
         height: 14px;
         line-height: 14px;
         margin-left: 8px;
         color: #757676;
         vertical-align: top;
       }
       .ruler{
          color: #757676;
           font-size:12px;
           line-height: 12px;
           vertical-align: top;
       }
       .mediate{
           color: #757676;
           font-size:12px;
           line-height: 12px;
           vertical-align: top;
       }


     }
     .arrangeModal{
       height: 78px;
        padding-left: 4px;
       padding-top: 10px;
       orangeBlock{
         vertical-align:top;
       }
       .arrangeStyle{
         vertical-align:top;
         font-size: 14px;
         color: #757676;
         line-height: 14px;
         margin-left: 8px;

       }
       .upright-text{
          font-size: 14px;
         color: #757676;
         line-height: 14px;
       }
       .across-text{
         font-size: 14px;
         color: #757676;
         line-height: 14px;
       }
     }
     .onePiece{
        height: 74px;
        padding-left: 4px;
        padding-top: 10px;
       .top{
          orangeBlock{
          vertical-align:top;
         }
         .descript{
           vertical-align:top;
           font-size: 14px;
           color: #757676;
           line-height: 14px;
           margin-left: 8px;
       }
       

       }
     }
     }
  }

</style>
