<template>

    <scroller class="view">

        <div class="header">
            <div class="userInfoContainer">
                <image class="userHeader" src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1495708260603&di=0483ee8cd377b75de3efb1bcabb169ec&imgtype=0&src=http%3A%2F%2Fimg4.duitang.com%2Fuploads%2Fblog%2F201407%2F16%2F20140716161852_jLtEJ.jpeg">

                </image>
                <text class="userName">叫我小詺</text>
            </div>
        </div>

        <table-view-cell class="cell" :item="item" v-for="(item,index) in itemList" :key="item.type" :isMark="item.isMark">

        </table-view-cell>
    </scroller>
</template>

<style>
    .rightItem
    {
        top: 68px;
        right: 29px;
        font-size: 32px;
        color: #666666;
    }
    .topPlaceholder
    {
        height: 128px;
        width: 750px;
    }

    .view {
        width: 750px;
        height: 1334px;
        background-color: white;
    }
    .header
    {
        /*flex-direction: ;*/
        justify-content: center;
        align-items: center;
        background-color: white;
        width: 750px;
        height: 484px;
        top: 0px;
        left: 0px;
    }
    .userInfoContainer
    {
        height: 214px;
        width: 375px;
        justify-content: center;
        align-items: center;
    }

    .userHeader
    {
        /* Oval 3 Copy: */
        background: #EBEBEB;
        width: 144px;
        height: 144px;
        border-radius: 72px;
    }
    .userName
    {
        /* 肖申克的救赎: */
        font-family: .PingFangSC-Regular;
        font-size: 30px;
        color: #333333;
        letter-spacing: 0;
        line-height: 30px;
        margin-top: 40px;
    }
    .cell
    {
        width: 750px;
        height: 88px;
        /*position: absolute;*/
    }

</style>

<script>
    import tableViewCell from '../tableViewCell/tableViewCell.vue'
//    let stream = weex.requireModule('stream')
//    let  apiHost = 'http://hulu.top'
    var host = 'http://localhost/'
    export default {
        data () {
            return {
                itemList:[
                    {
                        text:'开通会员',
                        navigaitonBarTitle:'名刊会会员',
                        image:'http://mkhioslocal/buyVIP',
                        detailText:'',
                        accessViewUrl:'http://mkhioslocal/arrowOfCell',
                        type:0,
                        actionUrl: host + 'dist/MineCenter/VIPCenterViewController.js',
                    },
                    {
                        text:'账户余额',
                        navigaitonBarTitle:'账户余额',
                        image:'http://mkhioslocal/myBalance',
                        detailText:'0.00',
                        accessViewUrl:'http://mkhioslocal/arrowOfCell',
                        type:1,
                        actionUrl: host + 'dist/MineCenter/AccountBalanceViewController.js',
                    },
                    {
                        text:'购买记录',
                        navigaitonBarTitle:'购买记录',
                        image:'http://mkhioslocal/buyHistory',
                        detailText:'',
                        accessViewUrl:'http://mkhioslocal/arrowOfCell',
                        type:2,
                        actionUrl: host + 'dist/MineCenter/BuyHistoryViewController.js',
                    },
                    {
                        text:'会员卡激活',
                        navigaitonBarTitle:'会员卡激活',
                        image:'http://mkhioslocal/activityVIP',
                        detailText:'',
                        accessViewUrl:'http://mkhioslocal/arrowOfCell',
                        type:3,
                        actionUrl: host + 'dist/MineCenter/ActivityVIPViewController.js',
                    },
                    {
                        text:'我赞过的',
                        navigaitonBarTitle:'我赞过的',
                        image:'http://mkhioslocal/mark',
                        detailText:'18',
                        accessViewUrl:'http://mkhioslocal/arrowOfCell',
                        refKey:'myMarkDetailLabel',
                        type:4,
                        isMark:true,
                        actionUrl: host + 'dist/MineCenter/MyMarkViewController.js',
                    },
                    {
                        text:'设置',
                        navigaitonBarTitle:'设置',
                        image:'http://mkhioslocal/setting',
                        detailText:'',
                        accessViewUrl:'http://mkhioslocal/arrowOfCell',
                        type:5,
                        actionUrl: host + 'dist/MineCenter/SettingViewController.js',
                    }

                ],
//                userInfo:{},
//                accessKey: 'mkh2a4ec304d1ff17e0|1bf142fe872eb12e7d3acb6e78ecf1a58166ca1d8bdc46610c09c4a8073cc9384103eb796110e9a0|e3040b4571ed00e8dbc32879dfbb8ad0|1495104633752',
            }
        },
        methods: {
            goEditPage()
            {

            }
        },
        components:{
            tableViewCell
        },
//        created:{
//
//        }

    }
</script>