<!-- 倒计时组件 -->
<template>
  <div>
      倒计时：<input type="text" v-model="time"> s
      <button @click="handleCountdown">{{ isCountdowning ? '停止' : '开始' }}</button>
  </div>
</template>

<script>
export default {
    data() {
        return {
            time: '',
            timer: null,
            isCountdowning: false
        }
    },
    methods: {
        handleCountdown() {
            if (this.isCountdowning) {
                window.clearInterval(this.timer)
                this.isCountdowning = false
            } else {
                this.timer = window.setInterval(() => {
                    if(this.time > 0) {
                        this.time -= 1
                        this.isCountdowning = true
                    } else {
                        window.clearInterval(this.timer)
                        this.isCountdowning = false
                    }
                }, 1000)
            }
        }
    }
}
</script>

<style>

</style>