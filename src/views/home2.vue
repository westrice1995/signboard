<template>
    <div class="page1">
        <div class="title"></div>
    </div>
</template>

<script>
export default {
    name: '',
    data() {
        return {
            activeName: 'month',// 默认显示近一月
            modal: false,
            selectRangeDate: [],
            startTime: '',
            endTime: '',
            optionStart: {
                disabledDate(date) { // 禁止选择今天之后的日期
                    return date && date.valueOf() > Date.now() - 86400000;
                }
            },
            optionEnd: {},
            resizeFn: null
        }
    },
    mounted() {
        window.addEventListener('resize', this.resizeFn);
    },
    methods: {
    },
}
</script>

<style lang="less">
.page1 {
    width: 7500px;
    height: 3071px;
    background: url('../assets/newImg/bg2.jpg') no-repeat;
    background-attachment:fixed;
    .title {
    }
}
</style>