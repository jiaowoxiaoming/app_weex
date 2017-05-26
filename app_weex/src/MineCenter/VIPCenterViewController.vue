<template>
    <div class="view">
        <div class="topPlacehold"></div>
        <div class="header">
            <div class="userInfoContainer">
                <image class="userHeader" src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1495708260603&di=0483ee8cd377b75de3efb1bcabb169ec&imgtype=0&src=http%3A%2F%2Fimg4.duitang.com%2Fuploads%2Fblog%2F201407%2F16%2F20140716161852_jLtEJ.jpeg">

                </image>
                <text class="userName">叫我小詺</text>
                <text class="vipDisc">开通名刊会会员，让阅读无限制</text>
            </div>
        </div>
    </div>
</template>

<style>
    .view {
        width: 750px;
        height: 1334px;
        background-color: #fff;
    }
    .topPlacehold
    {
        width: 750px;
        height: 128px;
        background-color: #fff;
    }
    .header
    {
        /*flex-direction: ;*/
        justify-content: center;
        align-items: center;
        background-color: white;
        width: 750px;
        height: 344px;
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
    .vipDisc
    {
        /* 开通名刊会会员，让阅读无限制: */
        font-family: .PingFangSC-Regular;
        font-size: 24px;
        color: #999999;
        letter-spacing: 0;
        margin-top: 30px;
    }

</style>

<script>

    import vipTableViewCell from '../tableViewCell/VIPCenterTableViewCell.vue'
    export default {
        data () {
            return {}
        },
        methods: {},
    }
</script>