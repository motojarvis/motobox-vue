<template>
    <!-- <el-row class="grid-top bg-purple">
        this is speed.
    </el-row> -->
    <div id="c1"></div>
</template>

<script>
import { Chart } from '@antv/g2';

const data = [
  { genre: 'Sports', sold: 275 },
  { genre: 'Strategy', sold: 115 },
  { genre: 'Action', sold: 120 },
  { genre: 'Shooter', sold: 350 },
  { genre: 'Other', sold: 150 },
];

// Step 1: 创建 Chart 对象
const chart = new Chart({
  container: 'c1', // 指定图表容器 ID
  width: 600, // 指定图表宽度
  height: 300, // 指定图表高度
});

// Step 2: 载入数据源
chart.data(data);

// Step 3: 创建图形语法，绘制柱状图
chart.interval().position('genre*sold');

// Step 4: 渲染图表
chart.render();

export default {
    name:'LeftScreen',
    // methods:{
    //     creatData() {
    //         const data = [];
    //         const val = (Math.random() * 6).toFixed(1);
    //         data.push({ value: +val });
    //         return data;
    //     },
    //     draw(data) {
    //         const val = data[0].value;
    //         const lineWidth = 25;
    //         chart.annotation().clear(true);
    //         // 绘制仪表盘背景
    //         chart.annotation().arc({
    //             top: false,
    //             start: [0, 1],
    //             end: [6, 1],
    //             style: {
    //             stroke: '#CBCBCB',
    //             lineWidth,
    //             lineDash: null,
    //             },
    //         });

    //         if (val >= 2) {
    //             chart.annotation().arc({
    //             start: [0, 1],
    //             end: [val, 1],
    //             style: {
    //                 stroke: color[0],
    //                 lineWidth,
    //                 lineDash: null,
    //             },
    //             });
    //         }

    //         if (val >= 4) {
    //             chart.annotation().arc({
    //             start: [2, 1],
    //             end: [4, 1],
    //             style: {
    //                 stroke: color[1],
    //                 lineWidth,
    //                 lineDash: null,
    //             },
    //             });
    //         }

    //         if (val > 4 && val <= 6) {
    //             chart.annotation().arc({
    //             start: [4, 1],
    //             end: [val, 1],
    //             style: {
    //                 stroke: color[2],
    //                 lineWidth,
    //                 lineDash: null,
    //             },
    //             });
    //         }

    //         if (val > 2 && val <= 4) {
    //             chart.annotation().arc({
    //             start: [2, 1],
    //             end: [val, 1],
    //             style: {
    //                 stroke: color[1],
    //                 lineWidth,
    //                 lineDash: null,
    //             },
    //             });
    //         }

    //         if (val < 2) {
    //             chart.annotation().arc({
    //             start: [0, 1],
    //             end: [val, 1],
    //             style: {
    //                 stroke: color[0],
    //                 lineWidth,
    //                 lineDash: null,
    //             },
    //             });
    //         }

    //         // 绘制指标数字
    //         chart.annotation().text({
    //             position: ['50%', '85%'],
    //             content: '合格率',
    //             style: {
    //             fontSize: 20,
    //             fill: '#545454',
    //             textAlign: 'center',
    //             },
    //         });
    //         chart.annotation().text({
    //             position: ['50%', '90%'],
    //             content: `${data[0].value * 10} %`,
    //             style: {
    //             fontSize: 36,
    //             fill: '#545454',
    //             textAlign: 'center',
    //             },
    //             offsetY: 15,
    //         });
    //         chart.changeData(data);
    //     },
    // },
    // mounted(){
    //     // 自定义Shape 部分
    //     registerShape('point', 'pointer', {
    //     draw(cfg, container) {
    //         const group = container.addGroup({});
    //         // 获取极坐标系下画布中心点
    //         const center = this.parsePoint({ x: 0, y: 0 });
    //         // 绘制指针
    //         group.addShape('line', {
    //         attrs: {
    //             x1: center.x,
    //             y1: center.y,
    //             x2: cfg.x,
    //             y2: cfg.y,
    //             stroke: cfg.color,
    //             lineWidth: 5,
    //             lineCap: 'round',
    //         },
    //         });
    //         group.addShape('circle', {
    //         attrs: {
    //             x: center.x,
    //             y: center.y,
    //             r: 9.75,
    //             stroke: cfg.color,
    //             lineWidth: 4.5,
    //             fill: '#fff',
    //         },
    //         });
    //         return group;
    //     },
    //     });


    //     draw(this.creatData());
    //     setInterval(function() {
    //     draw(this.creatData());
    //     }, 1000);
    //     const color = ['#0086FA', '#FFBF00', '#F5222D'];
    //     const chart = new Chart({
    //     container: 'container',
    //     autoFit: true,
    //     height: 500,
    //     padding: [0, 0, 30, 0],
    //     });
    //     chart.data(this.creatData());
    //     chart.animate(false);

    //     chart.coordinate('polar', {
    //     startAngle: (-9 / 8) * Math.PI,
    //     endAngle: (1 / 8) * Math.PI,
    //     radius: 0.75,
    //     });
    //     chart.scale('value', {
    //     min: 0,
    //     max: 6,
    //     tickInterval: 1,
    //     });

    //     chart.axis('1', false);
    //     chart.axis('value', {
    //     line: null,
    //     label: {
    //         offset: -40,
    //         style: {
    //         fontSize: 18,
    //         fill: '#CBCBCB',
    //         textAlign: 'center',
    //         textBaseline: 'middle',
    //         },
    //     },
    //     tickLine: {
    //         length: -24,
    //     },
    //     grid: null,
    //     });
    //     chart.legend(false);
    //     chart.tooltip(false);
    //     chart
    //         .point()
    //         .position('value*1')
    //         .shape('pointer')
    //         .color('value', (val) => {
    //             if (val < 2) {
    //             return color[0];
    //             } else if (val <= 4) {
    //             return color[1];
    //             } else if (val <= 6) {
    //             return color[2];
    //             }
    //         });
    // }
};
</script>