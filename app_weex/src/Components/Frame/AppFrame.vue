<template>
    <!--<div class="view">-->

    <!--</div>-->

    <!--<app-frame :tabarItems="tabbarItemsJsonString" :viewControllerItems="viewControllerItemsString"></app-frame>-->
    <AppFrame id='AppFrame' :tabarItems="tabbarItemsJsonString" :viewControllerItems="viewControllerItemsString"></AppFrame>
</template>

<style>
    .view {
        width: 750px;
        height: 1334px;
        background-color: #fff;
    }
</style>

<script>
    var TabbarItemSelectedImage = 'TabbarItemSelectedImage'

    var TabbarItemImage = 'TabbarItemImage'

    var ViewController = 'ViewController'

    var host = 'http://localhost/'//http://192.167.0.3:8081/

    var dirctoryPath = 'dist/'
    export default {
        data () {
            return {

                tabbarItemsJsonString:JSON.stringify(
                    [
                        {
//                            标题
                            title:'封面',
//                            没选中字体颜色
                            normalTitleColor:'999999',
//                            选中字体颜色
                            selectedTitleColor:'FF3C00',
//                            背景颜色
                            tintColor:'FF3C00',
//                            选中图片
                            selectedImage:TabbarItemSelectedImage + '1',
//                            没选中图片
                            image:TabbarItemImage + '1'
                        },
                        {
                            title:'发现',
                            normalTitleColor:'999999',
                            selectedTitleColor:'FF3C00',
                            tintColor:'FF3C00',
                            selectedImage:TabbarItemSelectedImage + '2',
                            image:TabbarItemImage + '2'
                        },
                        {
                            title:'书桌',
                            normalTitleColor:'999999',
                            selectedTitleColor:'FF3C00',
                            tintColor:'FF3C00',
                            selectedImage:TabbarItemSelectedImage + '3',
                            image:TabbarItemImage + '3'
                        },
                        {
                            title:'我',
                            normalTitleColor:'999999',
                            selectedTitleColor:'FF3C00',
                            tintColor:'FF3C00',
                            selectedImage:TabbarItemSelectedImage + '4',
                            image:TabbarItemImage + '4'
                        }
                    ]),
                viewControllerItemsString:JSON.stringify(
                    [
                        {
//                            导航栏标题
                            title:'',
//                            透明导航栏的字体颜色
                            clearTitleColor:'ffffff',
//                            高斯模糊导航栏的字体颜色
                            blurTitleColor:'000000',
//                            左边选项按钮
                            leftItemsInfo:
                                [
                                    {
//                                        原生调取 weex方法名
                                        aciton:'',
//                                        渲染 按钮的链接  如果以http开头 会渲染网络JSBundle 反之 渲染本地JSBundle
                                        itemURL:''
                                    }
                                ],
//                            右边选项按钮
                            rightItemsInfo:
                                [
                                    {
                                        aciton:'',
                                        itemURL:host + dirctoryPath + 'DemoRefreshRightItem.js',
//                                        设计图中container的大小
                                        frame:'{{0, 0}, {32, 16}}'
                                    }
                                ],
//                            把导航栏变成透明的
                            clearNavigationBar:true,
//                            把导航栏隐藏
                            hiddenNavgitionBar:false,
//                            导航栏背景颜色
                            navigationBarBackgroundColor:'',
//                            导航栏背景图片
                            navgationBarBackgroundImage:'',
//                            自定义标题视图的JSBundle地址 如果以http开头 会渲染网络JSBundle 反之 渲染本地JSBundle
                            customTitleViewURL:'',
                            rootViewURL:host + dirctoryPath + 'index.js',
                        },
                        {
                            title:'',
                            clearTitleColor:'333333',
                            blurTitleColor:'333333',
//                            leftItemsInfo:[{aciton:'',itemURL:''}],
//                            rightItemsInfo:[{aciton:'',itemURL:'item.js',frame:'{{0, 0}, {66, 32}}'}],
                            clearNavigationBar:false,
                            hiddenNavgitionBar:true,
                            navigationBarBackgroundColor:'',
                            navgationBarBackgroundImage:'',
                            customTitleViewURL:'',
                            rootViewURL:host + dirctoryPath + 'find.js',
                        },
                        {
                            title:'名刊会',
                            clearTitleColor:'000000',
                            blurTitleColor:'',
//                            leftItemsInfo:[{aciton:'',itemURL:''}],
//                            rightItemsInfo:[{aciton:'',itemURL:'item.js',frame:'{{0, 0}, {66, 32}}'}],
                            clearNavigationBar:true,
                            hiddenNavgitionBar:false,
                            navigationBarBackgroundColor:'',
                            navgationBarBackgroundImage:'',
                            customTitleViewURL:'',
                            rootViewURL:host + 'dist/components/Frame/ThirdViewController.js',
                        },
                        {
                            title:'',
                            clearTitleColor:'',
                            blurTitleColor:'',
                            leftItemsInfo:[{aciton:'',itemURL:''}],
                            rightItemsInfo:[{aciton:'',itemURL:host + 'dist/components/Frame/MKHRightItem.js',frame:'{{0, 0}, {33, 16}}'}],
                            clearNavigationBar:false,
                            hiddenNavgitionBar:true,
                            navigationBarBackgroundColor:'',
                            navgationBarBackgroundImage:'',
                            customTitleViewURL:'',
                            rootViewURL:host + 'dist/components/Frame/FifthViewController.js',
                        },

                    ]),
            };
        },
        methods: {}
    }
    module.exports = {
        created:function() {
            this.$el('AppFrame').focus();
        }
    }
</script>