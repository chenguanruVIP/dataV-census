<template>
    <div class="left-table-3">
        <p>各省人口数量</p>
        <dv-scroll-board :config="config" style="width:430px;height:440px" rowNum="10"/>
    </div>
</template>

<script>


export default {
    name: 'RightTable-2',
    data(){
        return {
            config:{
                rowNum:10,
                header:['省','数量','排名'],
                data: [
                    ['北　京', 21893095],
                    ['天　津', 13866009],
                    ['河　北', 74610235],
                    ['山　西', 34915616],
                    ['内蒙古', 24049155],
                    ['辽　宁', 42591407],
                    ['吉　林', 24073453],
                    ['黑龙江', 31850088],
                    ['上　海', 24870895],
                    ['江　苏', 84748016],
                    ['浙　江', 64567588],
                    ['安　徽', 61027171],
                    ['福　建', 41540086],
                    ['江　西', 45188635],
                    ['山　东', 101527453],
                    ['河　南', 99365519],
                    ['湖　北', 57752557],
                    ['湖　南', 66444864],
                    ['广　东', 126012510],
                    ['广　西', 50126804],
                    ['海　南', 10081232],
                    ['重　庆', 32054159],
                    ['四　川', 83674866],
                    ['贵　州', 38562148],
                    ['云　南', 47209277],
                    ['西　藏', 3648100],
                    ['陕　西', 39528999],
                    ['甘　肃', 25019831],
                    ['青　海', 5923957],
                    ['宁　夏', 7202654],
                    ['新　疆', 25852345],
                ]
            }
        }
    },
    mounted(){
        let a = this.config.data.sort( (a,b) => {
            return b[1] - a[1]
        })
        a.map( (item,index) => {
            a[index].push(index+1)
        })
        this.$set(this.config,'data',a)
    }
}
</script>
<style scoped lang="scss">
.left-table-3{
    color:#ffffff;
    p{
        font-size: 17px;
        font-weight: bold;
        margin-bottom:30px;
    }
}
</style>