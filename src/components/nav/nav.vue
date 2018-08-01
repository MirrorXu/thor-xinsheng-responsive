<template>
    <div class="nav">
        <div class="banxin">
            <img class="logo" src="./logo.png" alt="logo图">
            <div class="tabs">
                <span class="tab" v-for="v in navs" @click="linkTo(v.link)">{{ v.text }}</span>
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
    @import "../../less/reset-common";
    @import "../../less/var";

    @h: 126px;

    .nav {
        height: @h;
        /*border: 1px solid salmon ;*/
        .banxin {
            .banxin();
            display: flex;
            justify-content: space-between;
            height: inherit;
            .logo {
                @logoH:50px;
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
                    &:hover{
                        color: @blue;
                        /*cursor: pointer;*/
                        cursor: default;
                    }
                    &:last-child{
                        padding-right: 0;
                    }

                }
            }
        }
    }
    

</style>
