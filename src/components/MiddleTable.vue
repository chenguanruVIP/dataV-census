<template>
    <div id="china_map_box">
        <div id="china_map"></div>
    </div>
</template>

<script>
// import echarts from "echarts";
import * as echarts from 'echarts'
import 'echarts/map/china.js'
export default {
    data() {
        return {
        //echart 配制option  
            options: {
                tooltip: {
                triggerOn: "mousemove",   //mousemove、click
                padding:8,
                borderWidth:1,
                borderColor:'#409eff',
                backgroundColor:'rgba(255,255,255,0.7)',
                textStyle:{
                    color:'#000000',
                    fontSize:13
                },
                formatter: function(e, t, n) {
                    let data = e.data;
                    let context = `
                    <div>
                        <p><b style="font-size:15px;">${data.name}</b></p>
                        <p class="tooltip_style"><span class="tooltip_left">人数</span><span class="tooltip_right">${data.value}</span></p>
                        <p class="tooltip_style"><span class="tooltip_left">全国总人数</span><span class="tooltip_right">141177872</span></p>
                    </div>
                    `
                    return context;
                }
                },
                visualMap: {
                    show:true,
                    left: 26,
                    bottom: 40,
                    showLabel:true,
                    textStyle:{
                        color:'#ffffff',
                        fontSize:13
                    },
                    pieces: [
                        {
                            gte: 100000000,
                            label: ">= 1亿",
                            color: "#484891"
                        },
                        {
                            gte: 80000000,
                            lt: 100000000,
                            label: "8千万 - 1亿",
                            color: "#7373B9"
                        },
                        {
                            gte: 60000000,
                            lt:80000000,
                            label: "6千万 - 8千万",
                            color: "#9999CC"
                        },
                        {
                            gte: 40000000,
                            lt: 60000000,
                            label: "4千万 - 6千万",
                            color: "#B8B8DC"
                        },
                        {
                            gte: 30000000,
                            lt: 40000000,
                            label: "3千万 - 4千万",
                            color: "#D8D8EB"
                        },
                        {
                            gte: 20000000,
                            lt: 30000000,
                            label: "2千万 - 3千万",
                            color: "#F3F3FA"
                        },
                        {
                            lt:20000000,
                            label:'<2千万',
                            color: "#FAF4FF"
                        }
                    ]
                },
                geo: {
                map: "china",
                scaleLimit: {
                    min: 1,
                    max: 2
                },
                zoom: 1,
                top: 120,
                label: {
                    normal: {
                    show:true,
                    fontSize: "14",
                    color: "rgba(0,0,0,0.7)"
                    }
                },
                itemStyle: {
                    normal: {
                    //shadowBlur: 50,
                    //shadowColor: 'rgba(0, 0, 0, 0.2)',
                    borderColor: "rgba(0, 0, 0, 0.2)"
                    },
                    emphasis: {
                    areaColor: "#f2d5ad",
                    shadowOffsetX: 0,
                    shadowOffsetY: 0,
                    borderWidth: 0
                    }
                }
                },
                series: [
                {
                    name: "突发事件",
                    type: "map",
                    geoIndex: 0,
                    data:[]
                }
                ]
            },
        //echart data
            dataList:[
                {name:'北京',value:21893095},
                {name:'天津',value:13866009},
                {name:'河北',value:74610235},
                {name:'山西',value:34915616},
                {name:'内蒙古',value:24049155},
                {name:'辽宁',value:42591407},
                {name:'吉林',value:24073453},
                {name:'黑龙江',value:31850088},
                {name:'上海',value:24870895},
                {name:'江苏',value:84748016},
                {name:'浙江',value:64567588},
                {name:'安徽',value:61027171},
                {name:'福建',value:41540086},
                {name:'江西',value:45188635},
                {name:'山东',value:101527453},
                {name:'河南',value:99365519},
                {name:'湖北',value:57752557},
                {name:'湖南',value:66444864},
                {name:'广东',value:126012510},
                {name:'广西',value:50126804},
                {name:'海南',value:10081232},
                {name:'重庆',value:32054159},
                {name:'四川',value:83674866},
                {name:'贵州',value:38562148},
                {name:'云南',value:47209277},
                {name:'西藏',value:3648100},
                {name:'陕西',value:39528999},
                {name:'甘肃',value:25019831},
                {name:'青海',value:5923957},
                {name:'宁夏',value:7202654},
                {name:'新疆',value:25852345},
            ]
        };
    },
    methods: {
        //初始化中国地图
        initEchartMap() {
        let mapDiv = document.getElementById('china_map');
        let myChart = echarts.init(mapDiv);
        myChart.setOption(this.options);
        },
        //修改echart配制
        setEchartOption(){
        this.options.series[0]['data'] = this.dataList;
        }
    },
    created() {
        this.setEchartOption();
    },
    mounted() {
        this.$nextTick(()=>{
            this.initEchartMap();
        })
    }
};
</script>
 
<style>
    #china_map_box{
        width: 100%;
        height: 100%;
    }
    #china_map {
        width: 100%;
        height: 70vh;
        color: #ffffff;
    }
</style>