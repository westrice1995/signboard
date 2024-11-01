<template>
    <div class="page1">
        <div class="content">
            <div class="left">
                <div class="title1"><img style='width: 2300px' src="../assets/newImg/title_1.png" alt="" class="src">
                </div>
                <div class="leftTop">
                    <div class="leftCon">
                        <img src="../assets/zujian1/small_titile_1.png" alt="" class="src">
                        <div class="conBox">
                            <div class="corner-box first">
                                <div class="number">50</div>
                                <div class="text">覆盖小区(个)
                                </div>
                            </div>
                            <div class="corner-box">
                                <div class="number">66</div>
                                <div class="text">覆盖公共机构(个)</div>
                            </div>
                        </div>
                        <div class="conBox" style="position: relative;">
                            <div class="corner-box spcCorner">
                                <div>
                                    <div class="text"><span class="text1">覆盖总户数</span><span class="number2">15739</span>
                                    </div>
                                    <div class="text"><span class="text1">参与户数</span><span class="number2">12132</span>
                                    </div>
                                    <div class="text"><span class="text1">总设备数</span><span class="number2">192</span>
                                    </div>
                                </div>
                            </div>
                            <div style="display:inline-block;position: absolute;left: 598px;bottom:0">
                                <img class='usl' src="../assets/zujian1/tubiao1.png" alt="" srcset="">
                            </div>
                        </div>
                    </div>
                    <div class="rightCon">
                        <img src="../assets/zujian1/small_titile_2.png" alt="" class="src">
                        <div style="display:inline-block;position: absolute;left: 0px;bottom:30px">
                            <img class='usl' src="../assets/zujian1/tubiao2.png" alt="" srcset="">
                        </div>
                        <div class="lightSpan"><span class="span1">优</span><span class="span2">263次</span><span
                                class="span3">97.7%</span></div>
                        <div class="lightSpan"><span class="span1">良</span><span class="span2">2次</span><span
                                class="span3">0.74%</span></div>
                        <div class="lightSpan"><span class="span1">空</span><span class="span2">0次</span><span
                                class="span3">0.00%</span></div>
                        <div class="lightSpan"><span class="span1">差</span><span class="span2">4次</span><span
                                class="span3">1.49%</span></div>
                    </div>
                </div>
                <div class="leftTop">
                    <div class="leftCon">
                        <img src="../assets/zujian1/small_titile_1.png" alt="" class="src">
                    </div>
                    <div class="rightCon">
                        <img src="../assets/zujian1/small_titile_2.png" alt="" class="src">
                    </div>
                </div>
                <div class="leftTop">
                    <div class="leftCon">
                        <img src="../assets/zujian1/small_titile_1.png" alt="" class="src">
                    </div>
                    <div class="rightCon">
                        <img src="../assets/zujian1/small_titile_2.png" alt="" class="src">
                    </div>
                </div>
            </div>
            <div class="middle">
                <div class="title1"><img src="../assets/newImg/title_2.png" alt="" class="src"></div>
            </div>
            <div class="right">
                <div class="title1"><img src="../assets/newImg/title_3.png" alt="" class="src"></div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'page1',
    props: {

    },
    data() {
        return {
            resizeFn: null
        }
    },
    methods: {},
    watch: {
        selectRangeDate: function () {
            for (let i = 1; i < 18; i++) {
                this.$refs['chart' + i].setChart();
            }
        }
    },
    mounted() {
        this.resizeFn = this.$debounce(() => {
            // 通过捕获系统的onresize事件触发我们需要执行的事件
            for (let i = 1; i < 18; i++) {
                this.$refs['chart' + i].setChart();
            }
        }, 500)
        window.addEventListener('resize', this.resizeFn)

    },
    beforeDestroy() {
        window.removeEventListener('resize', this.resizeFn)
    }

}

</script>

<style lang="less">
img.usl {
    user-select: none;
    /* 禁止用户选择 */
    pointer-events: none;
}

.page1 {
    width: 5532px;
    height: 3265px;
    background: url('../assets/newImg/bg1.jpg') no-repeat;
    background-attachment: fixed;


    .content {
        padding-top: 140px;
        height: 100%;
        display: flex;
        justify-content: space-between;

        .left {
            width: 2580px;
            height: 100%;
            padding-left: 230px;

            .title1 {
                margin-top: 260px;
                position: relative;
                top: -7px;
                left: -17px;
            }

            .leftTop {
                display: flex;
                justify-content: space-between;

                .leftCon {
                    display: inline-block;
                }

                .rightCon {
                    display: inline-block;
                    position: relative;

                    .lightSpan {}
                }
            }
        }

        .middle {
            width: 1100px;
            height: 100%;
            border-left: 15px solid rgba(14, 47, 135, 0.5);

            .title1 {
                margin-top: 260px;
                position: relative;
                top: -18px;
                left: 0px;
            }
        }

        .right {
            width: 2580px;
            height: 100%;

            .title1 {
                margin-top: 260px;
                position: relative;
                top: 2px;
                left: 25px;
            }
        }
    }

    .corner-box {
        position: relative;
        display: inline-block;
        padding: 20px 40px;
        text-align: center;
        color: #ffffff;
        background-color: rgba(0, 0, 0, 0.5);
        font-size: 24px;
        position: relative;
        width: 420px;
        height: 247px;
        // csss实现四角边框
        box-shadow: 0 0 1.5vw #1f69b9b9 inset;
        background: linear-gradient(#b5f4ff, #b5f4ff) left top,
            linear-gradient(#b5f4ff, #b5f4ff) left top,
            linear-gradient(#b5f4ff, #b5f4ff) right top,
            linear-gradient(#b5f4ff, #b5f4ff) right top,
            linear-gradient(#b5f4ff, #b5f4ff) left bottom,
            linear-gradient(#b5f4ff, #b5f4ff) left bottom,
            linear-gradient(#b5f4ff, #b5f4ff) right bottom,
            linear-gradient(#b5f4ff, #b5f4ff) right bottom;
        background-repeat: no-repeat;
        border: 7px solid #1392ff;
        border-radius: 5px;
        background-size: 5px 30px, 30px 5px, 5px 30px, 30px 5px;

        .number {
            font-size: 120px;
            height: 120px;
            line-height: 120px;
            /* 字体大小 */
            font-weight: bold;
            /* 字体粗细 */
            background: linear-gradient(to bottom, #00bfff, #ffffff);
            /* 渐变颜色 */
            -webkit-background-clip: text;
            /* 背景裁剪为文字 */
            -webkit-text-fill-color: transparent;
            margin-top: 10px;
        }

        .text {
            margin-top: 5px;
            font-size: 40px;
        }
    }

    .corner-box.first {
        margin-left: 100px;
        margin-right: 80px;
        margin-top: 80px;
        margin-bottom: 100px;
    }

    .corner-box.spcCorner {
        width: 460px;
        height: 374px;
        margin-left: 100px;
        margin-bottom: 100px;
        display: flex;
        justify-content: center;

        /* 水平居中 */
        align-items: center;

        .text {
            font-size: 45px;
            width: 400px;
            line-height: 85px;

            .text1 {
                float: left;
                font-weight: bold
            }

            .number2 {
                background: linear-gradient(to bottom, #a4d7e7, #ffffff);
                /* 渐变颜色 */
                -webkit-background-clip: text;
                -webkit-text-fill-color: transparent;
                font-weight: bold;
                float: right;
            }
        }
    }



}
</style>