<template>
    <div class="right-table-1">
        <div class="r-n1">
            <div class="table-item">
                <p>人口地区分布</p>
                <dv-active-ring-chart :config="config1" class="chart-style"/>
            </div>
            <div class="table-item">
                <p>年龄构成</p>
                <dv-active-ring-chart :config="config2" class="chart-style" />
            </div>
        </div>
        <dv-decoration-2 style="height:10px;margin-top:20px" />
    </div>
</template>

<script>


export default {
    name: 'RightTable-1',
    data(){
        return {
            // 人口地区分布
            config1:{
                radius:'60%',
                activeRadius: '70%',
                lineWidth:15,
                digitalFlopToFixed:2,
                digitalFlopUnit:'%',
                color: ['#00baff', '#3de7c9', '#fff', '#ffc530', '#469f4b'],
                digitalFlopStyle: {
                    fontSize: 16,
                    fill: '#fff'
                },
                data: [
                    {
                    name: '东部地区',
                    value: 39.93
                    },
                    {
                    name: '中部地区占',
                    value: 25.83
                    },
                    {
                    name: '西部地区',
                    value: 27.12
                    },
                    {
                    name: '东北地区',
                    value: 6.98
                    }
                ]
            },
            // 年龄构成
            config2:{
                radius:'60%',
                activeRadius: '70%',
                lineWidth:15,
                digitalFlopToFixed:2,
                digitalFlopUnit:'%',
                color: ['#67e0e3', '#9fe6b8', '#96bfff', '#ffc530', '#469f4b'],
                digitalFlopStyle: {
                    fontSize: 16,
                    fill: '#fff'
                },
                data: [
                    {
                    name: '0—14岁',
                    value: 17.95
                    },
                    {
                    name: '15—59岁',
                    value: 63.35
                    },
                    {
                    name: '60岁及以上',
                    value: 18.70
                    }
                ]
            }
        }
    }
}
</script>
<style scoped lang="scss">
.right-table-1{
    color:#ffffff;
    width:100%;
    .r-n1{
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
    .table-item{
        p{
            font-size: 17px;
            font-weight: bold;
        }
    }
    .chart-style{
        width:10vw;
        height:20vh
    }
}
</style>