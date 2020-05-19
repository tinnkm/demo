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
            <span class="ruler"><input type="radio" v-model="textStyle" value="start"/>卡尺式</span>
            <span class="mediate"><input type="radio" v-model="textStyle" value="center"/>居中式</span>
          
          
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
              <aroundButton :data="vbtn" @selected="selected"></aroundButton>
            </div>
            <div class="across">
              <span class="across-text"><input type="radio" v-model="arrangement" value="horizontal"/>横排</span>
              <aroundButton :data="hbtn" @selected="selected"></aroundButton>
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
              <input v-model="height" type="text" >
          </div>
          <div></div>
        </div>
      </div>
      
    </div>
    <div class="disk">
      <span> 单位:mm</span>
      <block :width="width" :height="height" :data="data" :textStyle="textStyle" :textPosition="tp" :arrangement="arrangement"></block>
    </div>
    {{tp}}
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
  computed:{
    tp() {

      if (this.arrangement === 'vertical') {
        let flag = this.vbtn.some(item => item.key === this.textPosition)
        if (flag) {
          return this.textPosition
        }else{
          // 修正点击横向/或者纵向时,位置位置不对
          return this.vbtn[0].key
        }
      }else{
        let flag = this.hbtn.some(item => item.key === this.textPosition)
        if (flag) {
          return this.textPosition
        }else{
          // 修正点击横向/或者纵向时,位置位置不对
          return this.hbtn[0].key
        }
      }
    }

  },
  data () {
    return {
      width: '50',
      height: '20',
      arrangement: 'vertical',
      textPosition: 'right',
      textStyle: 'start',
      vbtn:[
        {
          key: 'left',
          lable: '左'
        },
         {
          key: 'right',
          lable: '右'
        }
      ],
      hbtn:[
        {
          key: 'top',
          lable: '上'
        },
         {
          key: 'bottom',
          lable: '下'
        }
      ],
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
  },
  methods:{
    selected(key){
      this.textPosition = key
      console.log(this.textPosition)
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
