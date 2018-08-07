<template>
    <div id="app">
        <Nav></Nav>
        <div class="sec-banner">
            <!--<h2>新闻中心</h2>-->
        </div>
        <div class="sec-news">
            <div class="banxin">
                <h2>新闻中心</h2>
                <div v-if="allNewsList.length ===   0" class="loading">
                    新闻数据获取中...
                </div>
                <template v-else>
                    <div class="newsBox-pc">
                        <template v-for="(v , i) in _setNewBox">
                            <div class="news-item">
                                <div class="news-item-bar" v-show="v.id !== openedNewsId"
                                     @click="changeOpenedNewsId(v.id)">
                                    <h5 class="title">{{v.title}}</h5>
                                    <span class="time">【{{v.time}}】</span>
                                </div>

                                <div class="news-item-open" v-show="v.id === openedNewsId">
                                    <div class="left" :style="{ backgroundImage:'url(' + v.titleImg +')'}">

                                    </div>
                                    <div class="right">
                                        <div class="top">
                                            <h4 class="title">{{v.title}}</h4>
                                            <span class="time">[ {{v.time || "--"}} ]</span>
                                        </div>
                                        <div class="bottom">
                                            <p>{{v.desc}}...   <a class="link" target="_blank"
                                                                  :href="'http://www.vlifebank.com/news.html?newsId='+v.id">详情 >></a>
                                            </p>
                                        </div>
                                    </div>
                                </div>

                            </div>

                        </template>
                    </div>

                    <div class="newsBox-m">
                        <template v-for="(v , i) in _setNewBox">
                            <a class="news-item" :href="'http://www.vlifebank.com/news.html?newsId='+v.id">
                                <div class="left" :style="{ backgroundImage:'url(' + v.titleImg +')'}"></div>
                                <div class="right">
                                    <h4 class="title">{{v.title}}</h4>
                                    <span class="time">[ {{v.time || "--"}} ]</span>
                                </div>
                            </a>

                        </template>
                    </div>

                    <div class="newsControl">

                        <i>第{{currentPage}}/{{pagesNum}} 页</i>
                        <span @click="changeCurrentPage('-') ">前一页</span>
                        <span @click="changeCurrentPage('+') ">后一页</span>

                    </div>
                </template>

            </div>
        </div>
        <Footer></Footer>

    </div>
</template>

<script>

	import Axios from "axios";  // 数据请求
	import Nav from '../../components/nav/nav.vue';
	import Footer from "../../components/footer/footer.vue"

	export default {
		name: 'app',
		data: function () {
			return {
				allNewsList: [],
				currentPage: 1,
				openedNewsId: undefined,
				serverApi: "http://api.vlifebank.com/vlifebank-api/news-list",
				pageNewsnum: 6,
				pagesNum: undefined
			}

		},
		components: {Nav, Footer},
		mounted() {
			Axios.get(this.serverApi).then((res) => {
				if (res.data) {
					this.allNewsList = res.data.data;
					if (this.allNewsList.length > 0) {
//						this.openedNewsId = this.allNewsList[0].id;
						this.pagesNum = Math.ceil(this.allNewsList.length / this.pageNewsnum);
					}
				}
			}).catch((err) => {
				console.log(err)
			})
		},
		computed: {
			_setNewBox() {
				let start = this.pageNewsnum * (this.currentPage - 1 );
				let end = start + this.pageNewsnum;
				let tempNewsList = this.allNewsList.slice(start, end)
				this.openedNewsId = tempNewsList[0].id;
				return tempNewsList
			}
		},
		methods: {
			changeOpenedNewsId(id) {
				this.openedNewsId = id;
			},
			changeCurrentPage(flag) {

				if (flag === "+") {
					if (this.currentPage < this.pagesNum) {
						this.currentPage = this.currentPage + 1
					}
				}

				if (flag === "-") {
					if (this.currentPage > 1) {
						this.currentPage = this.currentPage - 1
					}
				}

			}
		}
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

    @media (min-width: 768px) {
        #app {

            .sec-banner {
                background-image: url("../../source/news/banner.png");
                background-position: center;
                background-repeat: no-repeat;
                background-size: cover;
                height: 480px;

            }
            .sec-news {
                padding: 60px 0;
                .banxin {
                    color: @black_1;
                    .banxin();
                    h2 {
                        font-size: 30px;
                        font-weight: normal;
                        margin: 0;
                        padding-bottom: 20px;
                        border-bottom: 2px solid @gray_2;
                        margin-bottom: 10px;
                    }

                    .newsBox-pc {
                        color: @black_1;
                        .news-item {

                            padding: 20px 0;
                            border-bottom: 1px solid @gray_2;
                            /*&:last-child{*/
                            /*border-bottom: none;*/
                            /*}*/
                            .news-item-bar {
                                display: flex;
                                flex-direction: row;
                                justify-content: space-between;
                                align-items: center;

                                > .title {
                                    font-size: 16px;
                                    color: @black_1;
                                    font-weight: bolder;
                                    margin: 0;
                                    padding: 10px;
                                }
                                > .time {
                                    font-size: 16px;
                                    font-weight: normal;
                                }

                            }
                            .news-item-open {
                                display: flex;
                                flex-direction: row;
                                justify-content: space-between;
                                align-items: center;
                                .left {
                                    width: 220px;
                                    height: 120px;
                                    background-size: cover;
                                    background-repeat: no-repeat;
                                    background-position: center;
                                }
                                .right {
                                    width: 720px;
                                    .top {
                                        display: flex;
                                        flex-direction: row;
                                        justify-content: space-between;
                                        align-items: center;
                                        .title {
                                            width: 500px;
                                            font-size: 18px;
                                            color: @red;
                                            padding: 5px 0;
                                            margin: 0;
                                            font-weight: bolder;

                                        }
                                        .time {
                                            width: 120px;
                                            font-size: 16px;
                                            color: @red;
                                        }
                                    }
                                    .bottom {
                                        color: #555;
                                        font-size: 16px;
                                        line-height: 1.6;
                                        .link {
                                            display: inline-block;
                                            color: @red;
                                            /*display: inline-block;*/
                                            /*padding-left: 2em;*/
                                            font-size: 15px;
                                            text-decoration: underline;
                                        }
                                    }
                                }

                            }
                        }
                    }
                    .newsBox-m {
                        display: none;
                    }

                    .newsControl {
                        margin-top: 30px;
                        /*<!--border-top: 2px solid @gray_2;-->*/
                        padding-top: 10px;
                        display: flex;
                        justify-content: center;
                        align-items: flex-end;
                        > span {
                            width: 80px;
                            text-align: center;
                            font-size: 18px;
                            font-weight: bolder;
                            text-decoration: underline;
                            color: @blue-a;
                        }
                        > i {
                            font-size: 14px;
                            margin-left: -50px;
                        }
                    }
                }

            }
        }
    }

    @media (max-width: 768px) {
        #app {
            padding-top: 45px;
            .sec-banner {
                background-image: url("../../source/banner/m/3.png");
                background-position: center;
                background-repeat: no-repeat;
                background-size: cover;
                height: 200px;

            }
            .sec-news {
                .banxin {
                    color: @black_1;
                    width: 100%;
                    padding: 0 0.5rem;
                    h2 {
                        font-size: 1.4rem;
                        font-weight: 600;
                        border-bottom: 1px solid @gray_2;
                        padding: 1.5rem 0 0.5rem;
                        margin: 0;
                    }
                    .newsBox-pc {
                        display: none;
                    }
                    .newsBox-m {
                        box-sizing: border-box;
                        display: flex;
                        flex-direction: column;
                        justify-content: center;
                        align-items: center;
                        width: 100%;
                        color: @black_1;
                        .news-item {
                            width: 100%;
                            display: flex;
                            flex-direction: row;
                            justify-content: space-between;
                            align-items:center;
                            overflow: hidden;
                            text-decoration: none;
                            padding:0.5rem 3px;
                            border-bottom: 1px dotted @blcak_2;
                            .left {
                                width: 20% !important;
                                height: 5rem;
                                background-size: cover;
                                background-repeat: no-repeat;
                                background-position: center;
                            }
                            .right {
                                /*background: sandybrown;*/
                                width: 80% !important;
                                overflow: hidden;
                                display: flex;
                                flex-direction: column;
                                justify-content: center;
                                align-items: flex-end;
                                padding: 0.5rem;
                                .title {
                                    font-weight: normal;
                                    padding: 0;
                                    margin: 0;
                                    font-size: 0.9rem;
                                    text-decoration: none !important;
                                    color: @black_1;
                                }
                                .time {
                                    font-size: 0.7rem;
                                    color: @black_1;
                                }

                            }
                        }
                    }

                    .newsControl {
                        margin-top: 2rem;
                        margin-bottom: 2rem;
                        /*<!--border-top: 2px solid @gray_2;-->*/
                        display: flex;
                        justify-content: center;
                        align-items: flex-end;
                        > span {
                            text-align: center;
                            font-size: 0.9rem;
                            font-weight: bolder;
                            text-decoration: underline;
                            color: @blue-a;
                            display: inline-block;
                            padding: 0 1rem;
                        }
                        > i {
                            font-size: 0.9rem;
                            display: inline-block;
                            padding: 0 1rem;
                        }
                    }
                }

            }
        }
    }
</style>
