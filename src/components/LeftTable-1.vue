<template>
    <div class="left-table-1">
        <dv-charts :option="option" class="left-main"/>
        <dv-decoration-2 style="height:10px;" />
    </div>
</template>

<script>


export default {
    name: 'LeftTable-1',
    data(){
        return {
            option:{
                title: {
                    // show:false,
                    text: '性别构成',
                     style:{
                        fill:'#fff',
                    }
                },
                series: [
                    {
                        type: 'pie',
                        data: [
                            { name: '男性', value: 51.24 },
                            { name: '女性', value: 48.76 },
                        ],
                        radius: ['45%', '65%'],
                        insideLabel: {
                            show: false
                        },
                        outsideLabel: {
                            labelLineEndLength: 10,
                            formatter:'{name}-{value}%',
                            style: {
                                fontSize: 14,
                                fill: '#fff'
                            }
                        },
                    }
                ],
                color: ['#00baff',  '#ffc530',]
            }
        }
    }
}
</script>
<style scoped lang="scss">
.left-table-1{
    color:#ffffff;
    .left-main{
        height: 300px;
    }
}
</style>