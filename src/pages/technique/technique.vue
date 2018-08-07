<template>
    <div class="page">
        <Nav></Nav>
        <div class="sec-banner"></div>
        <div class="sec-yanjiubeijing">
            <div class="banxin">
                <div class="inner">
                    <div class="inner-left">
                        <h3>研究背景</h3>
                        <p>
                            肿瘤新抗原（Neo-antigen）：当肿瘤细胞发生基因突变，会产生区别于自身的异己成分，这类抗原被称为“肿瘤特异性抗原”(tumor specific antigens)，又被称为 neoantigens 。 这类抗原明显区别于自身成分，能够更有效地触发免疫反应，而且不会伤及自身。</p>
                    </div>
                    <div class="inner-right">
                        <img src="../../source/technique/1-1.png" alt="image">
                    </div>
                </div>
            </div>
        </div>


        <div class="sec-yanjiuyongtu">
            <div class="banxin">
                <h3>肿瘤新抗原检测的用途</h3>
                <p>(1)个性化肿瘤疫苗研制；</p>
                <p>(2)预后指导：精确预测肿瘤治疗疗效；</p>
            </div>
        </div>

        <div class="sec-yimiao">
            <div class="banxin">
                <h3>肿瘤新抗原个性化疫苗</h3>
                <div class="inner">
                    <div class="inner-left">
                        <p>根据肿瘤新抗原制备的疫苗被称为肿瘤个性化疫苗，因为新生抗原明显区别于自身成分，能够更有效地触发免疫反应，而且不会伤及自身。</p>
                        <img src="../../source/technique/1-2.png" alt="">
                    </div>
                    <div class="inner-right">
                        <div class="box">
                            <h4>案例：</h4>
                            <p>2017年7月5日《Nature》报道美国波士顿达纳-法伯癌症研究所Catherine Wu教授团队和德国缅因兹大学Ugur Sahin团队分别宣布了两项临床I期试验结果，针对不同肿瘤突变定制的个性化疫苗，在黑色素瘤患者治疗中大获成功。</p>
                            <p>Wu教授团队的临床试验结果显示，接种疫苗的6名黑色素瘤患者中，4人肿瘤完全消失，且32个月内无复发！另外2人肿瘤仍然存在，在接受辅助治疗后肿瘤也完全消失。</p>
                            <p>Ugur Sahin团队的结果显示，在13位接种疫苗的患者中，8人肿瘤完全消失且23月内无复发，其余5名患者由于接种疫苗时肿瘤已经扩散，有2人出现肿瘤缩小，其中1人接受辅助治疗后肿瘤完全消退！</p>
                            <img src="../../source/technique/1-3.png" alt="">
                        </div>
                    </div>
                </div>
            </div>
        </div>


        <Footer></Footer>
    </div>
</template>

<script>
	import Nav from "../../components/nav/nav.vue"
	import Footer from "../../components/footer/footer.vue"

	export default {
		name: 'app',
		data: function () {
			return {}
		},
		components: {Nav, Footer}

	}
</script>

<style lang="less">
    @import "../../less/reset-common";
    @import "../../less/var";

    @media (min-width: 768px) {
        .page {
            .sec-banner {
                height: 480px;
                background-image: url("../../source/technique/banner.png");
                background-position: center;
                background-size: cover;
                background-repeat: no-repeat;
            }
            .sec-yanjiubeijing {
                padding: 100px 0;
                .banxin {
                    .banxin();
                    .inner {
                        display: flex;
                        flex-direction: row;
                        justify-content: space-between;
                        align-items: center;
                        .inner-left, .inner-right {
                            width: 50%;
                            overflow: hidden;
                        }
                        .inner-left {
                            /*background: silver;*/
                            padding: 30px 30px 30px 0;
                            color: @black_1;
                            h3 {
                                font-size: 30px;
                                margin: 0;
                                padding: 0;
                                font-weight: normal;
                            }
                            p{
                                font-size: 16px;
                                line-height: 1.8;
                            }
                        }
                        .inner-right {
                            /*background: salmon;*/
                            display: flex;
                            justify-content: center;
                            > img {
                                display: block;
                                width: 90%;
                            }
                        }
                    }

                }

            }
            .sec-yanjiuyongtu{
                padding: 60px 0;
                background: @gray;
                .banxin{
                    .banxin();
                    color: @black_1;
                    h3 {
                        font-size: 30px;
                        margin: 0;
                        padding: 0;
                        font-weight: normal;
                        padding-bottom: 10px;
                    }
                    p{
                        font-size: 16px;
                        line-height: 1.8;
                        margin-bottom: 0;
                        margin-top: 10px;
                    }
                }

            }
            .sec-yimiao{
                padding: 60px 0 100px 0 ;
                .banxin{
                    .banxin();
                    color: @black_1;
                    h3{
                        font-size: 30px;
                        margin: 0;
                        padding: 0;
                        font-weight: normal;
                        padding-bottom: 30px;

                    }
                    .inner{
                        box-sizing: border-box;
                        display: flex;
                        flex-direction: row;
                        justify-content: space-between;

                        &-left , &-right{
                            width: 50%;
                        }

                        &-left{
                            padding-right: 60px;

                        }
                        &-right{
                            /*background: salmon;*/
                            padding-left: 30px;
                            .box{
                                padding: 30px;
                                background: @gray ;
                            }

                        }

                        p{
                            font-size: 16px;
                            line-height: 1.7;
                            text-indent: 2em;
                        }
                        img{
                            display: block;
                            width: 90%;
                        }

                        h4{
                            margin-top: 10px;
                            font-size: 26px;
                            font-weight: normal;
                        }

                    }
                }

            }

        }

    }
    @media (max-width:768px) {

        .page {
            padding-top: 45px;
            .sec-banner {
                height: 200px;
                background-image: url("../../source/banner/m/2.png");
                background-position: center;
                background-size: cover;
                background-repeat: no-repeat;
            }
            .sec-yanjiubeijing {
                .banxin {
                    margin-top: 2rem;
                    width: 100%;
                    padding: 0 0.5rem;
                    .inner {
                        display: flex;
                        flex-direction: column;
                        align-items: center;
                        .inner-left, .inner-right {
                            width: 100%;
                            overflow: hidden;
                        }
                        .inner-left {
                            /*background: silver;*/
                            padding: 1rem 1rem 1rem 0;
                            color: @black_1;
                            h3 {
                                font-size: 30px;
                                margin: 0;
                                padding: 0;
                                font-weight: normal;
                            }
                            p{
                                font-size: 16px;
                                line-height: 1.8;
                            }
                        }
                        .inner-right {
                            /*background: salmon;*/
                            display: flex;
                            justify-content: center;
                            align-items: center;
                            padding-bottom: 2rem;
                            > img {
                                display: block;
                                width: 90%;
                            }
                        }
                    }

                }

            }
            .sec-yanjiuyongtu{
                padding: 2rem 0;
                background: @gray;
                .banxin{
                    width: 100%;
                    padding: 0 0.5rem;
                    color: @black_1;
                    h3 {
                        font-size: 1.5rem;
                        margin: 0;
                        padding: 0;
                        font-weight: normal;
                        padding-bottom: 10px;
                    }
                    p{
                        font-size: 1rem;
                        line-height: 1.8;
                        margin-bottom: 0;
                        margin-top: 10px;
                    }
                }

            }
            .sec-yimiao{
                padding: 60px 0 2rem 0 ;
                .banxin{
                    width: 100%;
                    padding: 0 0.5rem;
                    color: @black_1;
                    h3{
                        font-size: 1.7rem;
                        margin: 0;
                        padding: 0;
                        font-weight: normal;

                    }
                    .inner{
                        box-sizing: border-box;
                        display: flex;
                        flex-direction: column;
                        justify-content: center;
                        align-items: center;
                        p{
                            font-size: 0.9rem;
                            line-height: 1.7;
                        }
                        img{
                            display: block;
                            width: 60%;
                            margin: 0 auto;
                        }

                        h4{
                            margin-top: 10px;
                            margin-bottom: 0;
                            padding-bottom: 1rem;
                            font-size: 26px;
                            font-weight: normal;
                        }
                        &-left , &-right{
                            width: 100%;
                        }

                        &-left{

                        }
                        &-right{
                            margin-top: 2rem;
                            .box{
                                padding: 30px;
                                background: @gray ;
                            }
                            img{
                                width: 100%;
                            }

                        }

                    }
                }

            }

        }

    }

</style>
