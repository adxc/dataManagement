<template>
  <div class="m-charts">
    <div id="myChart"></div>
    <div class="m-checkDate">
      <div class="u-date fc-green-1 active">今天</div>
      <div class="u-date fc-green-1">一周</div>
    </div>
    <div class="u-total">
      <div class="t-title font-18">全部告警数</div>
      <div class="total">
        <div class="total-box">
          <div class="font-32 fc-blue num">1069</div>
          所有的布控数
        </div>
        <div class="total-box ">
          <div class="font-32 fc-green num">352</div>
          所有的告警数
        </div>
      </div>
    </div>
    <el-button @click="changed"></el-button>
  </div>
</template>

<script>
import Bus from '../utils/bus'
export default {
  name: 'z-echarts',
  data () {
    return {
      'isCollapse': ''
    }
  },
  mounted () {
    this.drawLine()
    Bus.$on('isCollapse', isCollapse => {
      this.isCollapse = isCollapse
    })
  },
  watch: {
    isCollapse () {
      this.changed()
    }
  },
  methods: {
    changed () {
      let myChart = this.$echarts.init(document.getElementById('myChart'))
      console.log(myChart)
      setTimeout(function () {
        myChart.resize()
      }, 1000)
    },
    drawLine () {
      // 基于准备好的dom，初始化echarts实例
      let myChart = this.$echarts.init(document.getElementById('myChart'))
      this.myChart = myChart
      // 绘制图表
      let options = {
        aria: {
          show: true
        },
        title: {
          text: '告警系统',
          textStyle: {
            color: '#fff',
            fontSize: 18,
            fontWeight: 'lighter'
          },
          padding: 15
        },
        grid: {
          left: 55,
          top: 70
        },
        legend: {
          top: 15,
          right: 'right',
          width: 180,
          textStyle: {
            color: '#fff'
          },
          itemGap: 20,
          data: [{
            name: '布控总数',
            // 强制设置图形为圆。
            icon: 'rect',
            // 设置文本为红色
            textStyle: {
              color: '#fff'
            }
          }, {
            name: '告警总数',
            // 强制设置图形为圆。
            icon: 'rect',
            // 设置文本为红色
            textStyle: {
              color: '#fff'
            }
          }
          ]
        },
        backgroundColor: '#00A77D',
        color: ['#37A2DA'],
        tooltip: {
          trigger: 'axis'
        },
        xAxis: {
          type: 'category',
          boundaryGap: false,
          axisLine: {
            lineStyle: {
              color: '#fff'
            }
          },
          data: ['00.00-01:59', '04.00-05:59', '08:00-09:59', '12:00-13:59', '16:00-17:59', '20:00-21:59']
        },
        yAxis: {
          type: 'value',
          boundaryGap: false,
          data: ['0', '300', '600', '900', '1200', '1500'],
          splitLine: {
            lineStyle: {
              color: ['#00B07D']
            }
          },
          axisLine: {
            lineStyle: {
              color: '#fff'
            }
          }
        },
        series: [{
          name: '布控总数',
          type: 'line',
          color: '#fff',
          smooth: true,
          data: [0, 0, 500, 700, 900, 1100, 1300]
        }, {
          name: '告警总数',
          type: 'line',
          color: '#00ffff',
          smooth: true,
          data: [0, 0, 200, 200, 900, 1300, 1500]
        }]
      }
      myChart.setOption(options)
      window.onresize = myChart.resize
    }
  }
}
</script>

<style lang='postcss'>
  .m-charts{
    width: 45%;
    border-radius: 5px;
    overflow: hidden;
    position: relative;
    .m-checkDate{
      position: absolute;
      top: 15px;
      left: 100px;
      display: flex;
      width: 90px;
      height: 20px;
      border: 1px solid #239876;
      align-items: center;
      background: #78cfb6;
      border-radius: 2px;
      .u-date{
        width: 50%;
        text-align: center;
        height: 20px;
        line-height: 20px;
        cursor: pointer;
        &:first-child{
          border-right: 1px solid #239876;
        }
      }
      .active{
        background: #108161;
        color: #fff;
      }
    }
    #myChart{
      width: 100%;
      height: 250px;
    }
    .u-total{
      background: #fff;
      padding: 10px;
      border-radius: 0 0 5px 5px;
      .t-title{
        color: #666;
      }
      .total{
        display: flex;
        padding: 10px;
        align-items: center;
        justify-content: space-around;
        .total-box{
          text-align: center;
          font-size: 14px;
          .num{
            margin-bottom: 10px;
          }
        }
      }
    }
  }
</style>
