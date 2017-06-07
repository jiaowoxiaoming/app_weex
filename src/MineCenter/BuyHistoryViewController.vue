<template>
    <div class="view">
        <list class="tableView" >
            <cell class="header"></cell>
            <cell class="cell" v-for="item in itemList">
                <div class="cellContainerView">
                    <div class="leftView">
                        <text class="textLabel">{{item.text}}</text>
                        <text class="detailLabel">{{item.detailText}}</text>
                    </div>
                    <div class="rightView">
                        <text class="priceLabel">{{item.price}}</text>
                    </div>
                </div>
                <div class="line"></div>
            </cell>
        </list>
    </div>
</template>

<style>
    .line {
        width: 750px;
        border-width: 0.5px;
        border-color: #EBEBEB;
        left: 0px;
    }
    .header
    {
        width: 750px;
        height:128px;
    }
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
        /* -128.00: */
        font-family: .PingFangSC-Regular;
        font-size: 26px;
        color: #FF3C00;
        /*line-height: 14px;*/

    }
    .tableView
    {
        width: 750px;
        height: 1334px;
        background-color: #fff;
        flex-direction: column;
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
    .view {
        width: 750px;
        height: 1334px;
        background-color: #fff;
    }
</style>

<script>
    export default {
        data () {
            return {
                itemList:[
                    {
                        text:'年费会员',
                        detailText:'2016-12-30  17:15:38',
                        price:'-128.00'
                    },
                    {
                        text:'年费会员',
                        detailText:'2016-12-30  17:15:38',
                        price:'-128.00'
                    },
                    {
                        text:'年费会员',
                        detailText:'2016-12-30  17:15:38',
                        price:'-128.00'
                    },
                    {
                        text:'年费会员',
                        detailText:'2016-12-30  17:15:38',
                        price:'-128.00'
                    },
                ],

            }
        },
        methods: {

        }
    }
</script>