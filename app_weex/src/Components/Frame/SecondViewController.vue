<template>
    <list class="view">
        <cell class="headerView">
            <div class="headerViewtop">
                <!--新上架-->
                <div class="newPushView" @click="gotoPage" :item="action">
                    <image class="newPushImageView" src="http://plus.qikan.com.cn/mkh/new.png">
                        <div class="newPushViewText">
                            <text class="textstyle">新上架</text>
                            <text class="texttype">N e w  L i s t</text>
                        </div>
                    </image>

                </div>
                <!--都在读-->
                <div class="hotListView" @click="gotoPage" :item="action2">
                    <image class="hotListImageView" src="http://plus.qikan.com.cn/mkh/reading.png">
                        <div class="hotListViewText">
                            <text class="textstyle">都在读</text>
                            <text class="texttype">H o t  L i s t</text>
                        </div>
                    </image>

                </div>
            </div>
        </cell>
        <cell class="all">
            <div class="all-left"></div>
            <text class="all-text">全部</text>
            <div class="all-right"></div>
        </cell>
        <cell class="column-magaContent">
            <div class="cloumn-magaContent-list" :item="item"
                 v-for="item in magazines" type=14 @click="gotoPage">
                <div class="cloumn-magaContent-showdowWrap">
                    <image class="cloumn-magaContent-showdow"
                           src="http://hulu.leanapp.cn/weex/images/shadow/magazineShow-big.png">
                    </image>
                    <div class="magazinshadow-wrap">
                        <image class="cloumn-content-img magazin-img" :src="item.coverImage" >
                        </image>
                        <div class="magazin-border"></div>
                    </div>
                </div>
                <text class="magazin-name">{{item.resourceName}}</text>
            </div>
        </cell>
        <cell style="width: 750px;height: 49px;"></cell>
        <loading @loading="onloading" :display="loadingDisplay" style="justify-content: center">
            <text>{{loadingText}}</text>
        </loading>
    </list>
</template>

<style>
    .column-magaContent {
        flex-direction: row;
        justify-content: flex-start;
        flex-wrap: wrap;
        margin-top: 15;
        margin-left: 22;
        margin-bottom: 14;
    }

    .cloumn-content-list {
        height: auto;
        width: 210;
        overflow: hidden;
        margin-bottom: 25;
    }
    .cloumn-magaContent-list {

        width: 230;
        margin-right: 8;
        overflow: hidden;
    }
    .cloumn-magaContent-showdowWrap {
        width: 230;
        height: 296;
        position: relative;
        align-items: center;
        justify-content: center;
    }

    .cloumn-magaContent-showdow {
        width: 230;
        height: 296;
        position: absolute;
        top: 0;
        left: 0;
        z-index: 0;
    }

    .magazinshadow-wrap {
        position: relative;
        height: 274;
        width: 210;
        background-color: #F4F4F4;
        z-index: 1;
    }

    .cloumn-content-img {
        height: 274;
        width: 210;
    }

    .magazin-border {
        position: absolute;
        z-index: 2;
        width: 210;
        height: 274;
        left: 0;
        top: 0;
        opacity: 0.1;
        border-width: 1;
        border-color: #000000;
        border-bottom-style: solid;
    }

    .magazin-name {
        margin-left: 10;
        margin-top: 18;
        margin-bottom: 48;
        font-size: 25;
    }
    .all {
        width: 686;
        height: 54;
        margin-right: 32;
        margin-left: 32;
        flex-direction: row;
        position: relative;
        /*background-color: #0088fb;*/
        align-items: center;
        justify-content: space-between;
    }

    .all-left, .all-right {
        /*margin-top: 40;*/
        width: 296;
        border-width: 1;
        border-color: #ebebeb;
        border-style: solid;
    }

    .all-text {
        font-size: 24;
        color: #D3D1CE;
        letter-spacing: 0;
        text-align: center;

    }
    .newPushViewText,.hotListViewText
    {

        width: 124px;
        height: 80px;
    }
    .newPushView,hotListView
    {
        width: 355px;
        height: 202px;
        flex-direction: row;
        align-items: stretch;
        justify-content: flex-start;
    }
    .newPushImageView,.hotListImageView
    {
        width: 330px;
        height: 200px;
        background: rgba(0, 0, 0, 0.100);
        border-radius: 8px;
        align-items: center;
        justify-content: center;
    }
    .newPushViewText
    {
        width: 124px;
        height: 80px;
    }
    .textstyle {
        font-family: PingFangSC-Semibold;
        font-size: 40;
        color: #ffffff;
    }

    .texttype {
        font-family: Avenir-Medium;
        font-size: 20;
        color: #ffffff;
        letter-spacing: 0;
        text-align: center;
    }
    .view {
        width: 750px;
        height: 1334px;
        background-color: white;
    }
    .headerView
    {
        padding-left: 32px;
        padding-right: 32px;

        padding-top: 72px;
        padding-bottom: 0px;
        flex-direction: row;
        width: 750px;
        height: 302px;
    }
    .headerViewtop
    {
        width: 750px;
        height: 202px;
        flex-direction: row;
        /*justify-content: space-between;*/
        align-items: stretch;
    }

</style>

<script>
    let stream = weex.requireModule('stream')
    let modal = weex.requireModule('modal')
    let navigator = weex.requireModule('navigator')
    var appBasicModule = weex.requireModule('appmodule')
    let basicModule = weex.requireModule('HLBasicWeexModule');
    let homeModule = weex.requireModule('HLHomePageWeexModule');
    let loadingModule = weex.requireModule('HLLoadingWeexModule');
    let globalEvent = weex.requireModule('globalEvent');
    let apiHost = 'http://mkh.leanapp.cn'
    export default {
        data () {
            return {
                accessKey: 'mkh2a4ec304d1ff17e0|de04c1d2a2ea1646e33a6c184e8abbf9|fb685438c95ee78e2da6dcd0b6c4b221|1495029466557',
                list: [],
                magazines: [],
                magazineSaleRanks: [],
                loadingDisplay: 'hide',
                loadingText: '',
                start: 0,
                take: 12,
                action:{
                    title:'新上架',
                    activityType:2,
                    activityUrl:'dist/magazineList.js?type=11'
                },
                action2:{
                    title:'都在读',
                    activityType:2,
                    activityUrl:'/dist/magazineList.js?type=7'
                },
                catalogUrl:'dist/catalog.js',
                host:''
            }
        },
        methods: {
            gotoPage(e) {

                var obj = e.target.attr;
                var item = obj.item;

                if (item.activityType == 2) {
                    var params = {'url': this.host+item.activityUrl, 'animated': 'true',}
//                    navigator.push(params, function (e) {
//                    });
                    var navigtionBarInfo = {
                        title:item.title,
                        clearTitleColor:'333333',
                        blurTitleColor:'333333',
//                            leftItemsInfo:[{aciton:'',itemURL:''}],
//                            rightItemsInfo:[{aciton:'',itemURL:'item.js',frame:'{{0, 0}, {66, 32}}'}],
                        clearNavigationBar:false,
                        hiddenNavgitionBar:false,
                        navigationBarBackgroundColor:'',
                        navgationBarBackgroundImage:'',
                        customTitleViewURL:'',
//                        rootViewURL:host + dirctoryPath + 'Second' + ViewController + '.js',//'Second' + ViewController + '.weex.js',
                    };
                    try {
                        appBasicModule.openURL(params.url, {
                            animated: true,
                            navigtionBarInfo: navigtionBarInfo
                        }, function (result) {

                        });
                    }
                    catch (e)
                    {
                        var params = {'url':this.host+ item.activityUrl, 'animated': 'true',}
                        navigator.push(params, function (e) {
                        });
                    }
                }
                else if(item.activityType == 3){
                    basicModule.buyVIPWithCallback(function (ret) {
                    });
                }
                else {

                    var params = {'url': this.host+this.catalogUrl+'?resourceId='+item.resourceId+'&resourceListId='+item.resourceListId, 'animated': 'true',}

                    var navigtionBarInfo = {
                        title:item.resourceName,
                        clearTitleColor:'333333',
                        blurTitleColor:'333333',
                        clearNavigationBar:false,
                        hiddenNavgitionBar:false,
                        navigationBarBackgroundColor:'',
                        navgationBarBackgroundImage:'',
                        customTitleViewURL:'',
                    };
                    try {
                        appBasicModule.openURL(params.url, {
                            animated: true,
                            navigtionBarInfo: navigtionBarInfo
                        }, function (result) {

                        });
                    }catch (e)
                    {
                        navigator.push(params, function (e) {
                        });
                    }
                }
            },
            getData (callback) {
                return stream.fetch({
                    method: 'GET',
                    url: apiHost + '/api/recommend/list?type=12&start='+this.start+'&take=' + this.take,
                    type: 'json',
                    headers: {
                        accessKey: this.accessKey
                    }
                }, callback)
            },
            getAllData(){
                this.getData(res => {
                    this.magazines = res.data.result.items;
                    this.start = this.start + this.take;
                })
            },
            onloading() {
                this.loadingDisplay = 'show';
                let self = this;
                this.getData(res => {
                    if (res.data.result.items.length > 0) {
                        res.data.result.items.forEach(function (item) {
                            self.magazines.push(item);
                        })
                        this.start = this.start + this.take;
                    }
                    this.loadingDisplay = 'hide';
                })
            },
            getHost()
            {
                var reg = new RegExp("http://.*?/");
                var r =weex.config.bundleUrl.match(reg);
                if (r != null)return r[0];
                return null;
            }
        },

        created () {
            let self = this;
            self.day = new Date().getDate();
            this.host=this.getHost().replace('8081','8083')
            try {
                appBasicModule.accessKeyWithCallback(function (accessKey) {
                    self.accessKey = accessKey;
                });
                appBasicModule.userIdWithCallback(function (userId) {
                    self.userId = userId
                    self.getAllData();
                })
            }
            catch (e) {
                self.getAllData();
            }
        },
        mounted(){
            let self = this;
            globalEvent.addEventListener("refresh", function (e) {
                basicModule.accessKeyWithCallback(function (accessKey) {
                    self.accessKey = accessKey;
                });
                basicModule.userIdWithCallback(function (userId) {
                    self.userId = userId
                    self.getAllData();
                    loadingModule.endRefreshing();
                })
            });
        }
    }
</script>

