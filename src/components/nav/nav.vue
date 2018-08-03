<template>
    <div>
        <div class="nav-pc">
            <div class="banxin">
                <img class="logo" src="./logo.png" alt="logo图">
                <div class="tabs">
                    <span class="tab" v-for="(v , i) in  navs" @click="linkTo(v.link)" :key="i">{{ v.text }}</span>
                </div>
            </div>
        </div>
        <div class="nav-m">
            <div class="header">
                <div class="title">Thorgene</div>
                <div class="icon" @click="show = !show">
                    <i class="material-icons" v-if="!show">menu</i>
                    <i class="material-icons" v-else>close</i>
                </div>
            </div>
            <div class="content" :class="{'show':show}">
                <span class="item" v-for="(v , i) in  navs" @click="linkTo(v.link)" :key="i">{{ v.text }}</span>
            </div>
        </div>
    </div>
</template>

<script>
	export default {
		name: "Nav",
		data() {
			return {
				navs: [
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
					}
				],
                show:false
			};
		},
		methods: {
			linkTo: function (href) {
				window.location.href = href;
			}
		}
	};
</script>

<style lang="less">
    @import "../../less/reset-common";
    @import "../../less/var";

    @h: 126px;
    @media (min-width: 768px) {
        .nav-pc {
            height: @h;
            /*border: 1px solid salmon ;*/
            .banxin {
                .banxin();
                display: flex;
                justify-content: space-between;
                height: inherit;
                .logo {
                    @logoH: 50px;
                    height: @logoH;
                    width: auto;
                    margin-top: (@h - @logoH)/2;
                }
                .tabs {
                    height: inherit;
                    .tab {
                        height: inherit;
                        line-height: @h;
                        font-size: 20px;
                        color: @black;
                        padding-left: 39px;
                        padding-right: 39px;
                        /*font-weight: 600;*/
                        &:hover {
                            color: @blue;
                            /*cursor: pointer;*/
                            cursor: default;
                        }
                        &:last-child {
                            padding-right: 0;
                        }
                    }
                }
            }
        }

        .nav-m {
            display: none;
        }
    }

    @media (max-width: 767px) {
        .nav-pc {
            display: none;
        }

        @nav-H:48px;
        .nav-m {
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
            width: 100%;
            display: flex;
            flex-direction: column;
            .header {
                height:@nav-H;
                background: @blue;
                color: @white;
                display: flex;
                flex-direction: row;
                justify-content: space-between;
                padding: 0 10px;
                align-items: center;
                .icon {
                    display: inline-flex;
                }
            }
            .content {
                display: flex;
                flex-direction: column;
                background: @blue;
                color: @white;
                font-weight: bolder;

                /*改变*/
                height: 0;
                overflow: hidden;
                opacity: 0;
                transition: .6s;
                .item {
                    border-top: 1px solid rgba(119, 117, 116, 0.637);
                    height: @nav-H - 3;
                    line-height: 45px;
                    padding: 0 10px;
                    font-size: 15px;
                }
            }
            .show{
                height: auto;
                overflow: visible;
                opacity: 1;
            }
        }
    }
</style>
