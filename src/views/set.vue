<template >
  <div class="r">
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
              <span class="upright-text"><input type="radio" v-model="arrangement" value="vertical"/>竖排</span>
              <aroundButton></aroundButton>
            </div>
            <div class="across">
              <span class="across-text"><input type="radio" v-model="arrangement" value="horizontal"/>横排</span>
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
              <span >长</span>
              <input v-model="width" type="text" >
              <span >宽</span>
              <input v-model="width" type="text" >
          </div>
          <div></div>
        </div>
      </div>
      
    </div>
    <div class="disk">
      <span> 单位:mm</span>
      <block :width="width" :height="height" :data="data" :arrangement="arrangement"></block>
    </div>
  </div>
</template>

<script>
import orangeBlock from "@/components/orangeBlock/orangeBlock.vue"
import block from "@/components/block/block.vue"
import dotted from '@/components/dotted/dotted.vue'
import aroundButton from '@/components/button/aroundButton.vue'
export default {
  components:{
    orangeBlock,
    dotted,
    block,
    aroundButton
  },
  data () {
    return {
      width: '10',
      height: '10',
      arrangement: 'vertical',
      textPosition: '',
      style: '',
      data:[
        {
          color: '#810042',
          text: '50'
        },
        {
          color: '#f304ed',
          text: '40'
        },
        {
          color: '#0000ff',
          text: '15'
        },
        {
          color:'#61b8ff',
          text: '7'
        },
        {
          color:'#3dba3d',
          text: '1.6'
        },
        {
          color:'#a6f28f',
          text: '0.1'
        },
        {
          color:'#ffffff',
          text: '0'
        }
      ]
    }
  }

}
</script>
<style lang="less" scoped>
.r{
   display: flex;
  .setPanel{
      display: inline-block;
     width: 265px;
     height: 227px;
     background: #f8feff;
     margin-top: 20px;
     margin-left: 20px;
     box-shadow: #cdcdcd 0px 0px 50px 10px ;
     .title{
       background: #e3f1f5;
       .colorSet{
         position: relative;
         background: #429feb;
         color: #fff;
         font-size:12px;
         width: 70px;
         height: 32px;
         line-height: 32px;
         text-align: center;
         &::after{
           content:"";
           width:0;
           height:0;
          position: absolute;
          top: 12px;
          left: 70px;
        border-top:solid  5px transparent;
        border-left:solid 5px #429feb ;
       border-bottom:solid 5px transparent;

         }
       }
     }
     .content{

        padding: 0 12px;
     
        .numberModal{
         height: 32px;
         line-height: 32px;
         width: 100%;
         padding-left: 4px;
         display: flex;
         align-items: center;
           orangeBlock{
          //  vertical-align:top;
              flex:1
           }
          .numberStyle{
            flex:1;
            display: inline-block;
            font-size:14px;
           // line-height: 14px;
          // height: 25px;
           margin-left: 8px;
           color: #757676;
           vertical-align: top;
           }
          .ruler{
            flex:1;
            color: #757676;
            font-size:12px;
            line-height: 12px;
           // vertical-align: top;
           }
          .mediate{
            flex:1;
            color: #757676;
            font-size:12px;
            line-height: 12px;
           // vertical-align: top;
          }
        }
        .arrangeModal{
          height: 78px;
          padding-left: 4px;
          padding-top: 10px;
          .top{
            display: flex;
            align-items: center;
             orangeBlock{
               flex: 1;
            //   vertical-align:top;
            }
           .arrangeStyle{
             flex: 1;
            // vertical-align:top;
             font-size: 14px;
             color: #757676;
             line-height: 14px;
             margin-left: 8px;
            }
          }
         .upright{
            margin:4px 0 7px 0;
          .upright-text{
           font-size: 14px;
           color: #757676;
           line-height: 14px;
           }
         }
         .across-text{
          font-size: 14px;
          color: #757676;
          line-height: 14px;
          }
        }
        .onePiece{
          height: 4px;
          padding-left: 4px;
          padding-top: 10px;
          .top{
            display: flex;
            align-items: center;
              orangeBlock{
              // vertical-align:top;
              flex:1;
              }
             .descript{
                flex:1;
               // vertical-align:top;
               font-size: 14px;
               color: #757676;
               line-height: 14px;
               margin-left: 8px;
               margin-bottom: 10px;
              }

          }
        
          span{
            font-size: 14px;
           color: #757676;
           line-height: 14px;
           margin-right: 4px;
          }
          input{
            width: 35px;
            height: 20px;
            border:1px solid #bebcbc;
            margin-right: 13px;
            text-align: center;
          }
        }

     }
  }
  .disk{
    flex: 1;
    display: inline-block;
    margin-left: 70px;
    margin-top:50px;
     span{
      color: #000;
      font-size: 13px;
     }
  }
}
</style>
