<template>
  <div>
    <div style="width: 100%;height: 500px;top: 20px;" id="startChart" ref="startChart">

    </div>
  </div>
</template>

<script>
export default {
  name: 'organization',
  components: {},
  data () {
    return {}
  },
  methods: {
    showData: function () {
      let startChart = this.$echarts.init(this.$refs.startChart)
      let option = {
        title: {
          text: '体重变化统计图'
        },
        tooltip: {
          trigger: 'axis'
        },
        legend: {
          data: ['王凯', '笑语', '闵海', '赵杰', '霞姐', '晓军']
        },
        grid: {
          left: '3%',
          right: '4%',
          bottom: '3%',
          containLabel: true
        },
        toolbox: {},
        xAxis: {
          type: 'category',
          boundaryGap: false,
          data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            name: '王凯',
            type: 'line',
            smooth: true,
            color: 'orange',
            data: [120, 121, 134, 120, 135, 140, 148]
          },
          {
            name: '笑语',
            type: 'line',
            smooth: true,
            color: 'green',
            data: [140, 145, 143, 150, 160, 121, 150]
          },
          {
            name: '闵海',
            type: 'line',
            smooth: true,
            data: [150, 140, 145, 160, 150, 155, 130]
          },
          {
            name: '赵杰',
            type: 'line',
            smooth: true,
            color: 'blue',
            data: [120, 125, 135, 136, 140, 120, 110]
          }, {
            name: '霞姐',
            type: 'line',
            smooth: true,
            color: 'red',
            data: [120, 125, 135, 136, 140, 120, 110]
          },
          {
            name: '晓军',
            type: 'line',
            smooth: true,
            color: 'pink',
            data: [100, 102, 108, 110, 120, 110, 115]
          }
        ]
      }
      startChart.setOption(option)
      // 监听窗口变化事件
      window.addEventListener('resize', function () {
        startChart.resize(option)
      })
    }
  },
  computed: {},
  created () {
  },
  mounted () {
    this.showData()
  }
}
</script>

<style scoped>
</style>
