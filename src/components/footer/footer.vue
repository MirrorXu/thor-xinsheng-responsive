<template>
    <div class="footer">
        <div class="banxin">
            <div class="footer-top">
                <div class="footer-top-left">
                    <div class="footer-top-left-top">
                        <div class="links">
                            <span class="link" v-for="(v,i) in  links" @click="linkTo(v.link)"> {{v.text}} </span>
                        </div>
                        <div class="address"><img class="addressIcon" src="../../source/index/addressIcon.png">北京市经济技术开发区科创六街88号A1-2层</div>
                    </div>
                    <div class="footer-top-left-bottom">
                        客户服务热线：400 - 808 -8978
                    </div>
                </div>
                <div class="footer-top-right" >
                    <img src="./erweima.png"/>
                </div>
            </div>
            <div class="footer-bottom">
                <a href="http://www.thorgene.com">索真北京医学检验所有限公司</a>
                <a href="http://www.thorgene.com">索真（北京）医学科技有限公司</a>
                <span> COPYRIGHT © 2017,索真,ALL RIGHTS RESERVED.</span>
            </div>
        </div>
    </div>
</template>

<script>
	export default {
		name: '',
		data: function () {
			return {
				links: [
					{
						text: "关于我们",
						link: "./index.html"
					},
					{
						text: "技术方法",
						link: "./technique.html"
					},
					{
						text: "技术优势",
						link: "./advantage.html"
					},
					{
						text: "新闻中心",
						link: "./news.html"
					},
				]
			}
		},
		methods: {
			linkTo: function (href) {
				window.location.href = href
			}
		}

	}
</script>

<style lang="less">
    @import "../../less/var";

    @media (min-width: 768px) {
        @codeimgH:96px;
        .footer {
            background: @blue;
            color: @white;
            .banxin {
                .banxin();
                .footer-top {
                    padding-bottom: 10px;
                    padding-top: 15px;
                    border-bottom: 1px solid @white;
                    display: flex;
                    flex-direction: row;
                    align-content: space-between;
                    &-left{
                        width: 810px;
                        display: flex;
                        flex-direction: column;

                        @topH:40px;
                        &-top{
                            height: @topH;
                            padding-right: 20px;
                            display: flex;
                            flex-direction: row;
                            justify-content: center;

                            .links{

                                align-self: flex-end;
                                .link{

                                    font-size: 15px;
                                    padding: 0 15px;
                                    border-right: 1px solid @white;
                                    &:last-child{
                                        border-right: none;
                                    }
                                    &:hover{
                                        cursor: default;
                                    }
                                }
                            }
                            .address{
                                padding-left: 30px;
                                align-self: flex-end;

                                font-size: 14px;
                                .addressIcon{
                                    position: relative;
                                    vertical-align: bottom;
                                    margin-right: 5px;
                                }
                            }
                        }
                        &-bottom{
                            height: @codeimgH - @topH;
                            line-height: @codeimgH - @topH;
                            text-align: center;
                            align-self: center;
                            font-size: 22px;
                            font-weight: bolder;

                        }
                    }
                    &-right{
                        width: 130px;
                        >img{
                            display: block;
                            border: none;
                            width: @codeimgH;
                            height: @codeimgH;
                        }
                    }
                }
                .footer-bottom{
                    font-size: 14px;
                    padding: 3px 0;
                    text-align: center;
                    a{
                        color: @white;
                        text-decoration: none ;
                    }
                }
            }
        }
    }

    @media (max-width: 767px) {
        @codeimgH:96px;
        .footer {
            background: @blue;
            color: @white;
            .banxin {
                width: 100%;
                .footer-top {
                    padding-top: 20px;
                    border-bottom: 1px solid @white;
                    padding-bottom: 1rem;
                    display: flex;
                    flex-direction: row;
                    justify-content: space-around;
                    align-items: center;

                    &-left{
                        width: 70%;
                        display: flex;
                        flex-direction: column-reverse;
                        font-size: 14px;
                        &-top{

                            .links{
                                display: none;
                            }
                            .address{
                                padding-top: 10px;
                                font-size: 12px;
                                .addressIcon{
                                    width: 14px;
                                    position: relative;
                                    top: 3px;
                                }
                            }
                        }
                        &-bottom{

                        }
                    }
                    &-right{
                        width: 25%;
                        >img{
                            display: block;
                            border: none;
                            width: 100%;
                        }
                    }
                }
                .footer-bottom{
                    font-size: 12px;
                    padding: 4px 0;
                    text-align: center;
                    a{
                        display: none;
                        color: @white;
                        text-decoration: none ;
                    }
                }
            }
        }
    }



</style>
