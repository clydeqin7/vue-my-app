<!-- 事件 -->
<template>
  <div>
    name: {{ name || '--' }}
    <br/>
    <input :value="name" @change="handleChange"/> 
    <br/>
    <br/>
    <div @click="handleDivClick">
      <button @click="handleClick">重置成功</button>
      <button @click.stop="handleClick">重置失败</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: String
  },
  methods: {
    handleChange(e) {
      this.$emit('change', e.target.value)
    },
    handleDivClick() {
      this.$emit('change', '')
    },
    // eslint-disable-next-line
    handleClick(e) {
      // 都会失败
      // e.stopPropagation()
    }
   }
}
</script>

<style lang='scss' scoped>
</style>