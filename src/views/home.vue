<template>
    <div>
        <div class="page">
            <router-view></router-view>
        </div>
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
