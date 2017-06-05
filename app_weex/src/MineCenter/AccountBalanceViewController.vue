<template>
    <div class="view">
        <div class="header">
            <text class="balance">￥0.01</text>
        </div>
        <div class="sectionHeader">
            <text class="chongzhi">充值</text>
            <!--<div class="line"></div>-->
        </div>
        <div class="cell"  v-for="item in itemList" :item="item">
            <div class="cellContainerView">
                <div class="leftView">
                    <text class="priceLabel">{{item.price}}</text>
                </div>
                <div class="rightView">
                    <div class="chargeButtonView">
                        <text class="chargeButton">充值</text>
                    </div>
                </div>
            </div>
            <div class="line"></div>
        </div>
        <div class="footer">
            <text class="info">1. iPhone 和非 iOS 设备的充值不能相互通用，且虚拟产品必须通过苹果公司的应用内支付购买。</text>
            <text class="info">2. 通过 App Store 充值。</text>
            <text class="info">3. 充值失败/不会充值，请关注微信公众号【葫芦】，来解决问题。</text>
        </div>
    </div>
</template>

<style>
    .cell
    {
        width: 750px;
        height: 108px;
        background-color: #fff;
        /*align-items: center;*/
        /*justify-content: flex-end;*/
        flex-direction: column;
    }
    .cellContainerView
    {
        width: 750px;
        height: 107px;
        background-color: #fff;
        align-items: center;
        flex-direction: row;
    }
    .priceLabel
    {
        /* ￥128.00: */
        font-family: PingFangSC-Medium;
        font-size: 30px;
        color: #FF3C00;
        /*line-height: 32px;*/
        margin-right: 26px;
    }
    .leftView
     {
         width: 375px;
         height: 107px;
         align-items: flex-start;
         flex-direction: column;
         justify-content: center;
         padding-left: 32px;
     }
    .rightView
    {

        height: 107px;
        width: 375px;
        align-items: center;
        flex-direction: row;
        justify-content: flex-end;
        padding-right: 32px;
    }
    .chargeButtonView
    {
        /* Rectangle 5: */
        background-color: #FF3C00;
        border-radius: 24px;
        /*letter-spacing: 0;*/
        /*line-height: 28px;*/
        width: 136px;
        height: 48px;
    ;
        flex-direction: column;
        align-items: center;
        justify-content: center;

    }
    .chargeButton
    {
        /* 开通: */
        font-family: .PingFangSC-Medium;
        font-size: 26px;
        color: white;
        text-align: center
    }
    .line {
        width: 750px;
        border-width: 0.5px;
        border-color: #EBEBEB;
        /*left: 94px;*/
    }
    .info
    {
        /* 1. iPhone 和非 iOS 设备的: */
        font-family: .PingFangSC-Regular;
        font-size: 24px;
        color: #999999;
        letter-spacing: 0;
        line-height: 36px;
    }
    .balance
    {
        /* ￥0.01: */
        font-family: PingFangSC-Regular;
        font-size: 64px;
        color: #FF3C00;
        letter-spacing: 0;
        margin-bottom: 56px;
    }
    .sectionHeader
    {
        width: 750px;
        height: 80px;
        justify-content: center;
        align-items: flex-start;
        padding-left: 32px;
        flex-direction: column;
        background-color: #fff;
        border-bottom-color: #EBEBEB;
        border-bottom-width: 1px;
    }
    .chongzhi
    {
        /* 充值: */
        font-family: .PingFangSC-Regular;
        font-size: 30px;
        color: #999999;
    }
    .header
    {
        width: 750px;
        height: 304px;
        justify-content: flex-end;
        align-items: center;
        background-color: #F8F8F8;
    }
    .footer
    {
        width: 750px;
        height: 410px;
        padding: 32px;
    }
    .view {
        width: 750px;
        height: 1334px;
        background-color: #F8F8F8;
    }
</style>

<script>
    export default {
        data () {
            return {
                itemList:[
                    {
                        price:'¥12.00',
                    },
                    {
                        price:'¥12.00',
                    },
                    {
                        price:'¥12.00',
                    },
                    {
                        price:'¥12.00',
                    },
                    {
                        price:'¥12.00',
                    },
                    {
                        price:'¥12.00',
                    },

                ]
            }
        },
        methods: {

        }
    }
</script>