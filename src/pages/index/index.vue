<template>
    <div id="app">
        <Nav></Nav>
        <div class="banner">
            <div class="banxin">
                <h1 class="title">索真</h1>
                <p class="subTitle">肿瘤免疫基因组学研究领域的佼佼者！</p>
            </div>
        </div>

        <div class="sec-cancer">
            <div class="banxin">
                <h2 class="title2">专注癌症免疫组学</h2>
                <p>北京索真新生医学生物技术有限公司位于首都北京，由美国海归教授、基因检测专家、基因组大数据分析专家和基因医学解读专家联合创建。</p>
                <p>公司站在免疫基因组学研究的最前沿，始终相信：如果能进一步了解适应性免疫系统，将会对肿瘤的治疗产生重要指导作用。
                </p>
                <p>公司利用先进的高通量测序平台和生物信息学分析平台来检测肿瘤新生抗原。为推动癌症研究，索真立志于不断把免疫组学研究成果转化为服务于临床诊断和治疗评估的产品，以提高患者就医质量。
                </p>


                <div class="one img-show">
                    <img src="../../source/index/tu1.png" alt="">
                    <p>优质的NGS测序技术（放一张二代测序仪器）</p>
                </div>
                <div class="two">
                    <div class="img-show left">
                        <img src="../../source/index/tu3.png" alt="">
                        <p>强大的生物信息分析平台</p>
                    </div>
                    <div class="img-show right">
                        <img src="../../source/index/tu2.png" alt="">
                        <p>远超过国家标准的分子遗传学基因检测实验室</p>
                    </div>
                </div>
            </div>
        </div>

        <div class="sec-team">
            <div class="banxin">
                <h2 class="title2">核心运营团队</h2>
                <div class="team">
                    <div class="item chenqian">
                        <div class="item-top"></div>
                        <div class="item-bottom">
                            <h4 class="name">陈谦 <span class="name-title">生物医学</span></h4>
                            <div class="info">美国印第安纳大学医学院医学与分子遗传学系博士，美国约翰霍普金斯大学分子生物学和遗传学博士后，有丰富的基因检测和溶瘤病毒疫苗学术和工业界经验。
                            </div>
                        </div>
                    </div>

                    <div class="item liuhong">
                        <div class="item-top"></div>
                        <div class="item-bottom">
                            <h4 class="name ">刘泓 <span class="name-title">计算机数据</span></h4>
                            <div class="info">少年班，中科院计算所博士，研究成果应用于Facebook和阿里集团，有丰富的大数据和软件开发工作经验。
                            </div>
                        </div>
                    </div>
                    <div class="item zhanghongbing">
                        <div class="item-top"></div>
                        <div class="item-bottom">
                            <h4 class="name">张宏冰 <span class="name-title">肿瘤研究</span></h4>
                            <div class="info">美国宾夕法尼亚大学医学院博士，哈佛医学院博士后、讲师。现任中国医学科学院-北京协和医学院 美国中华医学基金会(CMB) 杰出教授、生理学博士生导师，北京协和医院兼职教授，国家杰出青年科学基金获得者。
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>


        <div class="sec-team">
            <div class="banxin">
                <h2 class="title2">核心专家顾问团队</h2>
                <div class="team">
                    <div class="item panduojia">
                        <div class="item-top"></div>
                        <div class="item-bottom">
                            <h4 class="name">潘多佳博士<span class="name-title">肿瘤基因研究</span></h4>
                            <div class="info">美国加州大学（UCLA）博士，美国加州大学（UC Berkeley）大学博士后。现为美国UT Southwest 医学中心生理系教授，系主任。美国霍华德休斯医学研究所研究员。国际肿瘤研究领域权威。特别是开创了HIPPO 基因通路在肿瘤中的功能研究。
                            </div>
                        </div>
                    </div>
                    <div class="item panfan">
                        <div class="item-top"></div>
                        <div class="item-bottom">
                            <h4 class="name ">潘帆博士 <span class="name-title">肿瘤免疫研究</span></h4>
                            <div class="info">美国约翰。霍普金斯大学医学院博士后。现为美国约翰霍普金斯大学医学院肿瘤中心副教授，为肿瘤免疫学做出了杰出贡献，其科学发现发表在nature、science、cell等学术杂志。
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="sec-research">
            <div class="banxin">
                <h2 class="title2">产品研发历程</h2>
                <div class="research-box">
                    <div class="item" v-for="(v , i) in history">
                        <h3 class="item-title">{{v.title}}</h3>
                        <p class="item-time">{{v.time}}</p>
                        <div class="cover">
                            <p>{{v.info}}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <div class="sec-partners">
            <h2 class="title2">合作伙伴</h2>
            <div class="out">
                <div class="con">
                    <img  src="http://www.vlifebank.com/8a83af79ec2695106a6ea18b1e5e1219.png"><!--
        --><img  src="http://www.vlifebank.com/8a83af79ec2695106a6ea18b1e5e1219.png">
                </div>
            </div>
        </div>


        <Footer></Footer>

    </div>
</template>

<script>

	import Nav from '../../components/nav/nav.vue';
	import Footer from "../../components/footer/footer.vue"


	export default {
		name: 'app',
		data: function () {
			return {
				history: [
					{
						title: "启动",
						time: "2016年12月",
						info: "索真肿瘤新抗原项目启动"
					},

					{
						title: "算法研发",
						time: "2017年9月",
						info: "索真肿瘤新抗原预算法内部测试成功"
					},

					{
						title: "首次实验",
						time: "2017年10月",
						info: "肿瘤细胞系（四癌种）新抗原预测实验完成"
					},

					{
						title: "合作研究",
						time: "2017年12月",
						info: "与科研单位（协和基础所）进行动物实验合作"
					},

					{
						title: "进入推广",
						time: "2018年3月",
						info: "动物实验以及回顾性研究完成，为临床试验做准备，计划在六月底递交临床试验申请"
					}
				]
			}
		},
		components: {Nav, Footer}
	}
</script>

<style lang="less">

    @import "../../less/reset-common";
    @import "../../less/var";
    // 图片效果 ，鼠标悬浮时，底部显示显示提示文字
    .img-show( @w:100% , @h:100% , @text-bgc:rgba(15,98,167,0.8)) {
        position: relative;
        z-index: 100;
        overflow: hidden;
        /*border: 3px solid red;*/
        > img {
            width: @w;
            height: @h;
            display: block;
        }
        > p {
            margin: 0;
            padding: 5px;
            position: absolute;
            z-index: 101;
            width: 100%;
            font-size: 16px;
            background: @text-bgc;
            /*top: 0;*/
            left: 0;
            bottom: -60px;
            text-align: left !important;
            color: @white;
            transition: 0.5s;
        }

        &:hover > p {
            bottom: 0;
        }

    }



    #app {

        .banner {
            .setBackgroundImgCover();

            .banxin {
                .banxin();
                padding-top: 160px;
                .title {
                    margin-top: 0;
                    color: @white;
                    font-size: 58px;
                }
                .subTitle {
                    color: @white;
                    font-size: 36px;
                }

            }
        }
        .sec-cancer {
            background: #ffffff;
            padding-bottom:50px ;
            .banxin {
                padding-top: 60px;
                .banxin();
                color: @blcak_2;
                .title2 {
                    .title2()
                }
                p {
                    text-align: center;
                    font-size: 16px;
                    line-height: 1.7;
                }

                .one {

                    .img-show();
                    margin-top: 50px;
                }
                .two {
                    margin-top: 10px;
                    display: flex;
                    flex-direction: row;
                    justify-content: space-between;
                    height: 330px;
                    overflow: hidden;
                    .left {
                        .img-show(@h:330px ,@w:660px);
                    }
                    .right {
                        .img-show(@h:330px; @w:330px);
                    }
                }
            }

        }

        .sec-team{
            background: @gray;
            padding-top: 30px;
            .banxin{
                .banxin();
                .title2{
                    .title2();
                }

                .team{
                    display: flex;
                    flex-direction: row;
                    justify-content: space-around;
                    .item{
                        @outerH:416px;
                        @topH:180px;
                        width: 312px;
                        height:@outerH;
                        border: 1px solid @blue;
                        flex-direction: column;

                        &-top{
                            height: @topH;
                            /*background: red;*/
                            background-position: center;
                            background-repeat: no-repeat;
                            background-size: cover;

                            transition: 0.3s;
                        }
                        &-bottom{
                            height: (@outerH - @topH) - 2;
                            color: @black_1;
                            padding: 15px;
                            .name{
                                margin-top: 0;
                                margin-bottom: 20px;
                                padding-top: 10px;
                                font-size: 26px;
                                &-title{
                                    font-weight: normal;
                                    font-size: 20px;
                                    display: inline-block;
                                    padding-left: 20px;
                                }
                            }
                            .info{
                                font-size: 15px;
                                color: inherit;
                            }

                            transition: 0.35s;
                        }
                        &:hover .item-bottom{
                            background: @blue;
                            color: @white;
                        }
                    }

                    .chenqian{
                        .item-top{
                            background-image: url("../../source/index/chenbo.png");
                        }
                        &:hover .item-top{
                            background-image: url("../../source/index/chenbo1.png");
                        }
                    }
                    .liuhong{
                        .item-top{
                            background-image: url("../../source/index/liuhong.png");
                        }

                        &:hover .item-top{
                            background-image: url("../../source/index/liuhong1.png");
                        }
                    }
                    .zhanghongbing{
                        .item-top{
                            background-image: url("../../source/index/zhanghongbing.png");
                        }

                        &:hover .item-top{
                            background-image: url("../../source/index/zhanghongbing1.png");
                        }
                    }
                    .panduojia{
                        .item-top{
                            background-image: url("../../source/index/panduojia.png");
                        }

                        &:hover .item-top{
                            background-image: url("../../source/index/panduojia1.png");
                        }
                    }
                    .panfan{
                        .item-top{
                            background-image: url("../../source/index/panfan.png");
                        }

                        &:hover .item-top {
                            background-image: url("../../source/index/panfan1.png");
                        }
                    }





                }
            }
            &:not(:first-child){
                padding-bottom: 60px;
            }
        }

        .sec-research{
            /*border: 1px solid orangered;*/
            padding: 50px 0 100px 0;
            .banxin {
                .banxin();
                .title2 {
                    .title2();
                }
                .research-box {
                    display: flex;
                    flex-direction: row;
                    justify-content: space-between;
                    .item {
                        width: 192px;
                        height: 230px;
                        background: @gray;
                        color: @black;
                        cursor: default;
                        &-title{
                            font-size: 30px;
                            font-weight: bolder;
                            padding-left: 30px;
                            margin-top: 80px;
                            margin-bottom: 10px;

                        }
                        &-time{
                            font-size: 16px;
                            font-weight: bolder;
                            padding-left: 30px;
                        }
                        position: relative;
                        .cover{
                            cursor: default;
                            position: absolute;
                            width: 100%;
                            height: 100%;
                            top: 0;
                            left: 0;
                            background:@blue-a ;
                            padding: 10px;
                            display: flex;
                            align-items: center;
                            justify-content: center;
                            p{
                                font-size: 16px;
                                color: @white;
                            }
                            opacity: 0;
                            transition: 0.5s;
                        }

                        &:hover .cover{
                            opacity: 1;
                        }
                    }
                }
            }
        }



        .sec-partners {
            padding-top: 30px;
            padding-bottom: 30px;
            background-color: #f9f9f9;
            .title2{
                .title2();
            }
            .out {
                width: 100%;
                padding: 10px 0 30px 0;
                margin: 0 auto;
                overflow: hidden;
                text-align: center;
                .con {
                    width: 10580px;
                    height: 150px;
                    animation: move 60s linear infinite normal;
                    animation-fill-mode: forwards;
                    overflow: hidden;
                    transform-origin: left top;
                    img {
                        display: inline-block;
                    }
                    .con:hover {
                        animation-play-state: paused;
                        -webkit-animation-play-state: paused;
                    }
                    @keyframes move {
                        0% {
                            transform: translateX(0px);
                        }
                        100% {
                            transform: translateX(-5290px);
                        }
                    }
                }

            }

        }



        /*padding-bottom: 200px;*/
    }
</style>
