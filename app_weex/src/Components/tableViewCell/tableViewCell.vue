<template>
    <div class="containerView" @click="goPage">
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

    let appBasicModule = weex.requireModule('XMWXModule')
    export default {
        props: {
//        cell的Model数据
            item: {
                type: Object,
                default: 'null'
            },
//        因为点赞和余额的DetailTextLabel的颜色不一样，需要给其一个判断条件
            isMark: {//这个cell是不是点赞Cell
                type: Boolean,
                default: false
            }
        },
        data () {
            return {}
        },
        methods: {
            goPage()
            {
                var navigtionBarInfo = {
                    title: '名刊会会员',
                    clearTitleColor:'333333',
                    blurTitleColor:'333333',
                    clearNavigationBar:true,
                    hiddenNavgitionBar:false,
                    navigationBarBackgroundColor:'',
                    navgationBarBackgroundImage:'',
                    customTitleViewURL:'',
                };
                appBasicModule.openURL(this.item.actionUrl,{
                    navigtionBarInfo:navigtionBarInfo,
                },function (result) {
                    
                })
            }


        }
    }
</script>