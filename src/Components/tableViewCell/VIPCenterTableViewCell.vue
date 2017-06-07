<template>
    <div class="containerView">
        <div class="view">
            <div class="leftView" v-if="!isConcessions">
                <text class="textLabel">{{item.text}}</text>
                <text class="detailLabel">{{item.detailText}}</text>
            </div>
            <div class="leftView" v-else="isConcessions">
                <div class="topText">
                    <text class="textLabel">{{item.text}}</text>
                    <div class="concessionsLabelView">
                        <text class="concessionsLabel">优惠</text>
                    </div>
                </div>
                <text class="detailLabel">{{item.detailText}}</text>
            </div>
            <div class="rightView">
                <text class="priceLabel">{{item.price}}</text>
                <div class="buyVIPButtonView">
                    <text class="buyVIPButton">开通</text>
                </div>

            </div>
        </div>
        <div class="line"></div>
    </div>

</template>

<style>
    .topText
    {
        flex-direction: row;
        justify-content: flex-start;
        align-items: center;
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
    .buyVIPButtonView
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
    .buyVIPButton
    {
        /* 开通: */
        font-family: .PingFangSC-Medium;
        font-size: 26px;
        color: white;
        text-align: center
    }
    .textLabel
    {
        /* 12个月: */
        font-family: .PingFangSC-Regular;
        font-size: 30px;
        color: #333333;
        line-height: 30px;
        /*left: 32px;*/
    }
    .detailLabel
    {
        /* 优惠季，原价180元，速来抢购: */
        font-family: .PingFangSC-Regular;
        font-size: 22px;
        color: #999999;
        /*left: 32px;*/
        margin-top: 8px;
    }
    .concessionsLabelView
    {
        /* Rectangle 11: */
        background-color: #FF3C00;
        border-radius: 6px;
        width: 64px;
        height: 36px;
        margin-left: 12px;
        align-items: center;
        justify-content: center;
    }
    .concessionsLabel
    {
        /* 优惠: */
        font-family: .PingFangSC-Regular;
        font-size: 24px;
        color: #FFFFFF;
        line-height: 26px;
        text-align: center;
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
    .containerView
    {
        width: 750px;
        height: 108px;
        background-color: #fff;
        /*align-items: center;*/
        /*justify-content: flex-end;*/
        flex-direction: column;
    }
    .view {
        width: 750px;
        height: 107px;
        background-color: #fff;
        align-items: center;
        flex-direction: row;
    }
    .line {
        width: 750px;
        border-width: 0.5;
        border-color: #EBEBEB;
        left: 0px;
    }
</style>

<script>
    export default {
        props: {
//        cell的Model数据
            item: {
                type: Object,
                default: 'null'
            },
//            是否有优惠
            isConcessions: {//这个cell是不是点赞Cell
                type: Boolean,
                default: false
            }
        },

        data () {
            return {

            }
        },
        methods: {}
    }
</script>