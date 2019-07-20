<template>
  <div>
<!--    <mt-swipe class="my-swipe" :auto="4000" :show-indicators="false">-->
<!--      <mt-swipe-item class="slide1">-->
<!--        <div id="chart_1" style="width:350px; height:200px"></div>-->
<!--      </mt-swipe-item>-->
<!--      <mt-swipe-item class="slide2">-->
<!--        <div id="chart_2" style="width:350px; height:200px"></div>-->
<!--      </mt-swipe-item>-->
<!--    </mt-swipe>-->
  </div>
</template>

<script>
import echarts from 'echarts'
export default {
  name: 'Profile',
  data () {
    return {
      data: [
        {value: 235, name: '视频广告'},
        {value: 274, name: '联盟广告'},
        {value: 310, name: '邮件营销'},
        {value: 335, name: '直接访问'},
        {value: 400, name: '搜索引擎'}
      ]
    }
  },
  mounted () {
    // 基于准备好的dom，初始化echarts实例
    var myChart1 = echarts.init(document.getElementById('chart_1'))
    // 绘制图表
    myChart1.setOption({
      title: {text: 'ECharts 入门示例'},
      series: [{
        name: '销量',
        type: 'pie',
        radius: '45%',
        data: this.data
      }]
    })
    var myChart2 = echarts.init(document.getElementById('chart_2'))
    myChart2.setOption({
      xAxis: {
        type: 'value'
      },
      yAxis: {
        type: 'value'
      },
      dataZoom: [
        { // 这个dataZoom组件，默认控制x轴。
          type: 'slider', // 这个 dataZoom 组件是 slider 型 dataZoom 组件
          start: 10, // 左边在 10% 的位置。
          end: 60 // 右边在 60% 的位置。
        }
      ],
      series: [
        {
          type: 'scatter', // 这是个『散点图』
          itemStyle: {
            opacity: 0.8
          },
          symbolSize: function (val) {
            return val[2] * 40
          },
          data: [['14.616', '7.241', '0.896'], ['3.958', '5.701', '0.955'], ['2.768', '8.971', '0.669'], ['9.051', '9.710', '0.171'], ['14.046', '4.182', '0.536'], ['12.295', '1.429', '0.962'], ['4.417', '8.167', '0.113'], ['0.492', '4.771', '0.785'], ['7.632', '2.605', '0.645'], ['14.242', '5.042', '0.368']]
        }
      ]
    }
    )
  }
}
</script>

<style>
  /*.my-swipe {*/
  /*  height: 200px;*/
  /*  color: #fff;*/
  /*  font-size: 30px;*/
  /*  text-align: center;*/
  /*}*/
</style>
