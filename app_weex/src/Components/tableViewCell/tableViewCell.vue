<template>
    <div class="containerView">
        <div class="view">
            <div class="leftView">
                <image class="imageView" :src="item.image"></image>

                <text class="textLabel" >{{item.text}}</text>
            </div>

            <div class="rightView" v-if="isMark">
                <text class="detailTextLabel" style="color: #999999;">{{item.detailText}}</text>
                <image class="accessView" :src="item.accessViewUrl"></image>

            </div>
            <div class="rightView" v-else="isMark">
                <text class="detailTextLabel" :refKey="item.refKey">{{item.detailText}}</text>
                <image class="accessView" :src="item.accessViewUrl"></image>
            </div>
        </div>
        <div class="line"></div>
    </div>

</template>

<style>
    .line {
        width: 656px;
        border-width: 0.5;
        border-color: #EBEBEB;
        left: 94px;
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
    .leftView
    {
        width: 375px;
        height: 87px;
        align-items: center;
        flex-direction: row;
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
    .view {
        width: 750px;
        height: 87px;
        background-color: #fff;
        align-items: center;
        flex-direction: row;
        /*justify-content: space-around;*/


    }
    .imageView
    {
        /*top: 15px;*/
        left: 30px;
        width: 36px;
        height: 36px;
    }
    .textLabel
    {
        left: 58px;
        font-size: 30px;
        color: #333333;
    }
    .detailTextLabel
    {

        font-size: 26px;
        color: #FF3C00;

    }
    .accessView
    {
        width: 50px;
        height: 50px;
        /*right: 16px;*/
    }
</style>

<script>
    export default {
        props: {
            item: {
                type: Object,
                default: 'null'
            },
            isMark: {
                type: Boolean,
                default: false
            }
        },
        data () {
            return {}
        },
        methods: {}
    }
</script>