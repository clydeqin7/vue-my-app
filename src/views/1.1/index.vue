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
      <a-tab-pane key="event" tab="事件">
        <Event
         :name="name" 
         @change="handleEventChange"
        ></Event>
      </a-tab-pane>
    </a-tabs>
  </div>
</template>

<script>
import Props from './Props.vue'
import Event from './Event.vue'
export default {
  components: { Props, Event },
  data () {
    return {
      type: 'danger',
      name: ''
    }
  },
  methods: {
    handlePropChange(val) {
      this.type = val
    },
    handleEventChange(val) {
      this.name = val
    } 
  }
}
</script>

<style lang='scss' scoped>
</style>