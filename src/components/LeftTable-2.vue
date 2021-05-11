<template>
    <div class="left-table-2">
        <div class="table-title">人口排名</div>
        <dv-capsule-chart :config="config" style="width:100%;height:400px" />

    </div>
</template>

<script>


export default {
    name: 'LeftTable-2',
    data() {
        return {
            config:{
                unit:"单位/万",
                showValue:true,
                data:[
                    {
                        name: '广东',
                        value: 12601
                    },
                    {
                        name: '山东',
                        value: 10152
                    },
                    {
                        name: '河南',
                        value: 9963
                    },
                    {
                        name: '江苏',
                        value: 8474
                    },
                    {
                        name: '四川',
                        value: 8367
                    },
                    {
                        name: '河北',
                        value: 7461
                    },
                    {
                        name: '湖南',
                        value: 6644
                    },
                    {
                        name: '浙江',
                        value: 6456
                    },
                    {
                        name: '安徽',
                        value: 6102
                    },
                    {
                        name: '湖北',
                        value: 5775
                    }
                ]
            }
        }
    }
}
</script>
<style scoped lang="scss">
.left-table-2{
    color:#ffffff;
    .table-title{
        font-size: 17px;
        font-weight: bold;
    }
}
</style>