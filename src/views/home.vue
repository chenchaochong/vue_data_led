<!--
 * @Author: daidai
 * @Date: 2022-01-12 14:23:32
 * @LastEditors: Please set LastEditors
 * @LastEditTime: 2022-04-28 14:22:06
 * @FilePath: \web-pc\src\pages\big-screen\view\home.vue
-->
<template>
  <div
    id="index"
    ref="appRef"
    class="index_home"
    :class="{ pageisScale: isScale }"
  >
    <div class="bg">
      <dv-loading v-if="loading">Loading...</dv-loading>
      <div v-else class="host-body">
        <!-- 头部 s -->
        <div class="d-flex jc-center title_wrap">
          <div class="zuojuxing"></div>
          <div class="youjuxing"></div>
          <div class="guang"></div>
          <div class="d-flex jc-center">
            <div class="title">
              <span class="title-text">江苏中睿珂琳环保科技有限公司数字化服务平台</span>
            </div>
          </div>
          <div class="timers">
            {{ dateYear }} {{ dateWeek }} {{ dateDay }}
            <i
              class="blq-icon-shezhi02"
              style="margin-left: 10px"
              @click="showSetting"
            ></i>
          </div>
        </div>
        <!-- 头部 e-->
        <!-- 内容  s-->
        <router-view></router-view>
        <!-- 内容 e -->
      </div>
    </div>
    <Setting ref="setting" />
  </div>
</template>

<script>
import drawMixin from '../utils/drawMixin'
import { formatTime } from '../utils/index.js'
import Setting from './setting.vue'
export default {
  mixins: [drawMixin],
  components: { Setting },
  data() {
    return {
      timing: null,
      loading: true,
      dateDay: null,
      dateYear: null,
      dateWeek: null,
      weekday: ['周日', '周一', '周二', '周三', '周四', '周五', '周六'],
    }
  },
  filters: {
    numsFilter(msg) {
      return msg || 0
    },
  },
  computed: {},
  created() {},
  mounted() {
    this.timeFn()
    this.cancelLoading()
  },
  beforeDestroy() {
    clearInterval(this.timing)
  },
  methods: {
    showSetting() {
      this.$refs.setting.init()
    },
    timeFn() {
      this.timing = setInterval(() => {
        this.dateDay = formatTime(new Date(), 'HH: mm: ss')
        this.dateYear = formatTime(new Date(), 'yyyy-MM-dd')
        this.dateWeek = this.weekday[new Date().getDay()]
      }, 1000)
    },
    cancelLoading() {
      setTimeout(() => {
        this.loading = false
      }, 500)
    },
  },
}
</script>

<style lang="scss">
@import './home.scss';
</style>
