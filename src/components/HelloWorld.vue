<template>
    <div class="main-box">
        <dv-full-screen-container>
            <div class="head-box">
                <div class="hd-left">
                    <!-- 68844万人女性，我的另一半在哪里 -->
                </div>
                <div class="hd-middle">第七次全国人口普查统计</div>
                <div class="he-right">
                    退出系统
                </div>
            </div>
            <dv-border-box-1 class="main-container">
                <dv-border-box-8 class="left-box" :dur="10">
                    <left-table-1></left-table-1>
                    <left-table-2 style="margin-top:20px"></left-table-2>
                    <!-- <left-table-3></left-table-3> -->
                </dv-border-box-8>
                <dv-border-box-11  class="middle-box" title="全国人口分布图">
                    <middle-table></middle-table>
                </dv-border-box-11>
                <dv-border-box-8 class="right-box" :reverse="true" :dur="10">
                    <right-table-1></right-table-1>
                    <right-table-2></right-table-2>
                </dv-border-box-8>
            </dv-border-box-1>

        </dv-full-screen-container>
    </div>
</template>

<script>
import LeftTable1 from './LeftTable-1'
import LeftTable2 from './LeftTable-2'
import LeftTable3 from './LeftTable-3'
import MiddleTable from './MiddleTable'
import RightTable1 from './RightTable-1'
import RightTable2 from './RightTable-2'
export default {
    name: 'HelloWorld',
    components:{
        LeftTable1,
        LeftTable2,
        LeftTable3,
        RightTable1,
        RightTable2,
        MiddleTable
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.main-box{
    width: 100%;
    height: 100%;
    #dv-full-screen-container{
        background-image: url('../assets/bg.png');
        background-size: 100% 100%;
        -webkit-box-shadow: 0 0 3px #00f;
        box-shadow: 0 0 3px #00f;
        display: -webkit-box;
        display: -ms-flexbox;
        display: flex;
        -webkit-box-orient: vertical;
        -webkit-box-direction: normal;
        -ms-flex-direction: column;
        flex-direction: column;
    }
    .head-box{
        width: 100%;
        height: 70px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-size:26px;
        font-weight: bold;
        color:#ffffff;
        box-sizing: border-box;
        padding:0px 20px;
        .hd-left{
            font-size: 14px;
            font-weight: normal;
            color: #67C23A;
        }
        .he-right{
            width: 90px;
            height: 36px;
            display: flex;
            align-items: center;
            justify-content: center;
            align-items: center;
            font-size: 18px;
            font-weight: normal;
        }
    }
    .main-container{
        height: calc(100vh - 80px);
        ::v-deep .border-box-content {
            padding: 20px;
            box-sizing: border-box;
            display: flex;
            justify-content: space-between;
        }
        .left-box{
            width: 25%;
            ::v-deep .border-box-content{
                display: flex;
                flex-direction: column;
                justify-content: space-between;
            }
        }
        .middle-box{
            width: 48%;
            ::v-deep .border-box-content{
                padding: 60px 20px 20px 20px;
                box-sizing: border-box;
            }
        }
        .right-box{
            width: 25%;
            ::v-deep .border-box-content{
                display: flex;
                flex-direction: column;
            }
        }
    }
}
</style>
