<template>
    <div class="contain">
          <span>  数值在</span>
          <el-button type="primary" plain class="button">左</el-button>
          <el-button type="primary" plain class="button"> 右</el-button>
    </div>
</template>
<script>
export default {
    
}
</script>
<style lang="less" scoped>
.contain{
    display: inline-block;
    margin-left: 20px;
    span{
        font-size: 14px;
        color: #757676;
        margin-right: 5px;
    }
    .button{
        width: 15px;
        height: 12px;
        margin: 0;
        font-size: 12px;
        line-height: 12px;
        text-align: center;
        border-radius: none;
    }
    
}
</style>