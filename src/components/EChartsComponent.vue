<template>
    <div ref="echartsContainer" style="width: 100%; height: 400px;"></div>
  </template>
  
  <script>
  // 引入 ECharts
  import * as echarts from 'echarts';
  
  export default {
    name: 'EChartsComponent',
    mounted() {
      // 组件挂载后初始化图表
      this.initChart();
    },
    methods: {
      // 初始化图表
      initChart() {
        // 获取图表容器
        const chart = echarts.init(this.$refs.echartsContainer);
  
        // 配置图表的选项
        const options = {
          title: {
            text: 'ECharts 示例',
          },
          tooltip: {},
          xAxis: {
            data: ['A', 'B', 'C', 'D', 'E'],
          },
          yAxis: {},
          series: [
            {
              name: '示例数据',
              type: 'bar',
              data: [5, 20, 36, 10, 10],
            },
          ],
        };
  
        // 使用配置项
        chart.setOption(options);
  
        // 添加点击事件
        chart.on('click', function (params) {
          alert(`你点击了 ${params.name} 数据，值为 ${params.value}`);
        });
      },
    },
  };
  </script>
  
  <style scoped>
  /* 你可以为图表设置一些样式 */
  </style>
  