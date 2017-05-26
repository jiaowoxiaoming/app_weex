<template>
    <div class="containerView">
        <div class="view">
            <div class="leftView" v-if="isConcessions">
                <text class="textLabel">{{item.title}}</text>
                <text class="detailLabel">{{item.detailText}}</text>
            </div>
            <div class="leftView" v-else="isConcessions">
                <div class="topText">
                    <text class="textLabel">{{item.title}}</text>
                    <text class="concessionsLabel">优惠</text>
                </div>
                <text class="detailLabel">{{item.detailText}}</text>
            </div>
            <div class="rightView">
                <text class="priceLabel">{{item.price}}</text>
                <text class="buyVIPButton">开通</text>
            </div>
        </div>
        <div class="line"></div>
    </div>

</template>

<style>
    .textLabel
    {
        /* 12个月: */
        font-family: .PingFangSC-Regular;
        font-size: 15px;
        color: #333333;
        line-height: 15px;
    }
    .detailLabel
    {
        /* 优惠季，原价180元，速来抢购: */
        font-family: .PingFangSC-Regular;
        font-size: 11px;
        color: #999999;
    }
    .concessionsLabel
    {
        /* Rectangle 11: */
        background: #FF3C00;
        border-radius: 3px;
        /* 优惠: */
        font-family: .PingFangSC-Regular;
        font-size: 12px;
        color: #FFFFFF;
        line-height: 13px;
    }
    .leftView
    {
        width: 375px;
        height: 87px;
        align-items: center;
        flex-direction: column;
        justify-content: flex-start;
    }
    .rightView
    {

        height: 87px;
        width: 375px;
        align-items: center;
        flex-direction: row;
        justify-content: flex-end;

    }
    .containerView
    {
        width: 750px;
        height: 88px;
        background-color: #fff;
        /*align-items: center;*/
        /*justify-content: flex-end;*/
        flex-direction: column;
    }
    .view {
        width: 750px;
        height: 1334px;
        background-color: #fff;
    }
</style>

<script>
    export default {
        props()
        {
            item:{
                type: Object,
                default: 'null,
            }
            isConcessions:{
                type:Boolean,
                default:false,
            }
        },

        data () {
            return {

            }
        },
        methods: {}
    }
</script>