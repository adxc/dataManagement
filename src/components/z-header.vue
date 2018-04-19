<template>
  <div class="g-hd">
    <div class="logo font-18"><img src="../assets/header/logo3.png" alt="">载德数据分析平台</div>
    <div class="m-navbar">
      <label for="" class="font-16">案件:</label>
      <el-select v-model="value" placeholder="请选择">
        <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value"></el-option>
      </el-select>
      <div class="u-navbar">
        <div class="m-message font-16">
          <i class="iconfont icon-xiaoxi font-20">
            <i class="new font-14">18</i>
          </i>
          告警
        </div>
        <div class="m-tool font-16">
          <i class="iconfont icon-tool font-20"></i>
            工具
        </div>
        <div class="m-setting font-16">
          <i class="iconfont icon-shezhi font-20"></i>
          设置
        </div>
        <div class="m-help font-16">
          <i class="iconfont icon-jiufuqianbaoicon09 font-20"></i>帮助
        </div>
        <div class="m-exit font-16">
          <i class="iconfont icon-tuichu font-20"></i>退出
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'z-header',
  data () {
    return {
      options: [
        {
          value: '1',
          label: '案件1'
        },
        {
          value: '2',
          label: '案件2'
        },
        {
          value: '3',
          label: '案件3'
        },
        {
          value: '4',
          label: '案件4'
        },
        {
          value: '5',
          label: '案件5'
        }
      ],
      value: ''
    }
  }
}
</script>

<style lang='postcss' scoped>
  .g-hd{
    flex: 0 0 auto;
    background: #3899b9;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 20px;
    .logo{
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .m-navbar{
      display: flex;
      align-items: center;
      justify-content: space-around;
      label{
        margin-right: 10px;
      }
      .u-navbar{
        display: flex;
        align-items: center;
        .m-message, .m-tool,.m-setting,.m-help,.m-exit{
          display: flex;
          align-items: center;
          margin-left: 10px;
          cursor: pointer;
          .new{
            position: absolute;
            display: block;
            width: 25px;
            height: 20px;
            color: #fff;
            background: #de0001;
            text-align: center;
            line-height: 20px;
            border-radius: 10px;
            top: 0;
            cursor: pointer;
          }
        }
      }
    }
  }
</style>
