<template>
    <div class="page">
        <Nav></Nav>
        <div class="sec-banner">
        </div>
        <div class="sec-title">
            <div class="banxin">
                <h2 class="title2">索真技术优势</h2>
                <p>
                    肿瘤新抗原研发最大的挑战来自于需要将肿瘤基因生物学、大数据分析和临床医学结合。索真肿瘤新抗原组建了一只由相关领域的顶级专家组成的技术团队。肿瘤新抗原研发最大的挑战来自于需要将肿瘤基因生物学、大数据分析和临床医学结合。索真肿瘤新抗原组建了一只由相关领域的顶级专家组成的技术团队。
                </p>
            </div>
        </div>
        <div class="sec-info">
            <div class="banxin">
                <h3>医学肿瘤基因检测团队</h3>
                <p>
                    索真肿瘤基因医学专家来自美国顶级医学院----霍普金斯医学院，其研究成果发表在顶级国际学术刊物如Cell, Development Cell, Hepatology, Genes & Development等，并具有溶瘤病毒疫苗工业界经验。</p>
                <h3>大数据分析团队</h3>
                <p>索真大数据分析团队来自顶级数据分析研究机构----中国科学院计算技术研究所，其研究成果应用于facebook和阿里巴巴集团等。</p>
                <h3>临床医学合作团队</h3>
                <p>索真医学临床合作团队来自国内顶级医院----北京协和医院。</p>
                <div class="img-box">
                    <img src="../../source/advantage/tu1.png" alt="肿瘤新抗原预测PipeLine图">
                </div>
            </div>
        </div>
        <div class="sec-yanzhi">
            <div class="banxin">
                <div class="title2">研制个性化肿瘤疫苗</div>
                <div class="container">
                    <h3>产品介绍</h3>
                    <p>肿瘤个性化疫苗，因为其新生抗原明显区别于自身成分，能够更有效地触发免疫反应，不会伤及自身。</p>
                    <img src="../../source/advantage/tu4.png" alt="">


                    <h3>个体化肿瘤疫苗临床试验</h3>
                    <p>肿瘤个性化疫苗，因为其新生抗原明显区别于自身成分，能够更有效地触发免疫反应，不会伤及自身。</p>
                    <div class="liucheng">
                        <div class="text-div">
                            <p>参与人留取组织样本、癌旁组织样本</p>
                        </div>
                        <div>
                            <span class="line"></span>
                        </div>
                        <div class="text-div">
                            <p>测序与数据分析</p>
                        </div>
                        <div>
                            <span class="line"></span>
                        </div>
                        <div class="text-div">
                            <p>根据预测结果合成疫苗</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <br><br><br>
        <Footer></Footer>
    </div>
</template>

<script>
	import Nav from "../../components/nav/nav.vue"
	import Footer from "../../components/footer/footer.vue"

	export default {
		name: 'advantage',
		data() {
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
                background-image: url("../../source/advantage/banner.png");
                background-position: center;
                background-size: cover;
                background-repeat: no-repeat;
            }
            .sec-title {
                padding: 40px;
                .banxin {
                    .banxin();
                    .title2 {
                        .title2();
                    }
                    p {
                        text-align: center;
                        color: @black_1;
                        line-height: 2;
                    }
                }
            }
            .sec-info {
                background: @gray;
                padding: 50px 0;
                .banxin {
                    .banxin();
                    h3 {
                        margin-top: 30px;
                        color: @black_1;
                        font-size: 30px;
                        margin-bottom: 30px;
                        font-weight: normal;
                    }
                    p {
                        color: @blcak_2;
                        font-size: 16px;
                    }
                    img {
                        display: block;
                        width: 60%;
                        margin: 30px auto;
                        margin-bottom: 0;
                    }

                }
            }

            .sec-yanzhi {
                padding: 50px 0;
                .banxin {
                    .banxin();
                    .title2 {
                        .title2();
                    }
                    .container {
                        h3 {
                            margin-top: 30px;
                            color: @black_1;
                            font-size: 30px;
                            margin-bottom: 30px;
                            font-weight: normal;
                        }
                        p {
                            color: @blcak_2;
                            font-size: 16px;
                        }
                        img {
                            display: block;
                            width: 70%;
                            margin: 80px auto;
                            margin-bottom: 0;
                        }

                        .liucheng {
                            margin-top: 50px;
                            display: flex;
                            flex-direction: row;
                            justify-content: center;
                            /*background: skyblue;*/
                            align-items: center;
                            > div {
                                width: 150px;
                                height: 150px;
                                position: relative;
                                > p {
                                    position: absolute;
                                    top: 40%;
                                    left: 50%;
                                    width: 80%;
                                    /*background: seagreen;*/
                                    transform: translate(-50%, -50%);
                                }
                                > .line {
                                    position: absolute;
                                    display: block;
                                    height: 4px;
                                    width: 100px;
                                    top: 50%;
                                    left: 50%;
                                    transform: translate(-50%, -50%);
                                    background: @blue-a;
                                }

                            }
                            .text-div {
                                background: @gray;
                                transition: 0.5s;
                                &:hover {
                                    background: @blue-a;
                                    > p {
                                        color: white;
                                    }
                                }
                            }

                        }
                    }

                }

            }
        }
    }

    @media (max-width: 768px) {
        .title2() {
            font-size: 1.5rem;
            text-align: center;
            color: #333;
            font-weight: normal;
        }
        .page {
            padding-top: 45px;
            .sec-banner {
                height: 200px;
                background-image: url("../../source/banner/m/4.png");
                background-position: center;
                background-size: cover;
                background-repeat: no-repeat;
            }
            .sec-title {
                .banxin {
                    width: 100%;
                    padding: 0 0.5rem;
                    .title2 {
                        .title2()
                    }
                    p {
                        text-align: left;
                        font-size: 1rem ;
                        color: @black_1;
                        line-height: 2;
                        text-indent: 2rem;
                    }
                }
            }
            .sec-info {
                background: @gray;
                padding: 1rem 0;
                .banxin {
                    padding: 0 0.5rem;
                    h3 {
                        color: @black_1;
                        font-size: 1.3rem;
                        font-weight: normal;
                        margin: 1rem 0;
                    }
                    p {
                        color: @blcak_2;
                        font-size: 0.9rem;
                        line-height: 1.8;
                    }
                    img {
                        display: block;
                        width: 90%;
                        margin: 30px auto;
                        margin-bottom: 0;
                    }

                }
            }
            .sec-yanzhi {
                padding: 2rem 0;
                .banxin {
                    .banxin();
                    padding: 0 .5rem;
                    .title2 {
                        .title2();
                    }
                    .container {
                        h3 {
                            color: @black_1;
                            font-size: 1.3rem;
                            margin:1.5rem 0 0.7rem;
                            font-weight: normal;
                        }
                        p {
                            color: @blcak_2;
                            font-size: 0.9rem;
                            line-height: 1.8;
                        }
                        img {
                            display: block;
                            width: 70%;
                            margin: 2rem auto;
                            margin-bottom: 0;
                        }

                        .liucheng {
                            margin-top: 0;
                            display: flex;
                            flex-direction: column;
                            align-items: center;
                            > div {
                                width: 60% !important;
                                margin-top: 1rem;
                                &:first-child{
                                    margin-top: 0;
                                }
                                > p {
                                    text-align: center;
                                    color: @white;
                                }
                                > .line {
                                }
                            }

                            .text-div{
                                width: 30%;
                                background: linear-gradient(-5deg, #006699  ,#5aa9e2 , #006699);
                                box-shadow: 1px 2px 3px 1px rgba(56, 56, 56, 0.6);
                            }

                        }
                    }

                }

            }
        }
    }


</style>
