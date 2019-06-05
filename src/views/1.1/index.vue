<!--  -->
<template>
  <div>
    <a-tabs>
      <a-tab-pane key="props" tab="属性">
        <Props
          name="Hello Vue!"
          :type="type"
          :is-visible="false"
          :on-change="handlePropChange"
          title="属性Demo"
          class="test1"
          :class="['test2']"
          :style="{ marginTop: '20px' }"
          stype="margin-top: 10px"
        ></Props>
      </a-tab-pane>
    </a-tabs>
  </div>
</template>

<script>
import Props from './Props.vue'
export default {
  components: { Props },
  data () {
    return {
      type: 'danger'
    }
  },
  methods: {
    handlePropChange(val) {
      this.type = val
    }
  }
}
</script>

<style lang='scss' scoped>
</style>