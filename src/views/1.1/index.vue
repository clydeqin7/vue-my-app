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
      <a-tab-pane key="slot" tab="插槽">
        <h2>2.6 新语法</h2>
        <SlotDemo>
          <p>default slot</p>
          <template v-slot:title>
            <p>title slot 1</p>
            <p>title slot 2</p>
          </template>
          <template v-slot:item="props">
            <p>item slot-scope {{ props }}</p>
          </template>
        </SlotDemo>
        <h2>老语法</h2>
        <SlotDemo>
          <p>default solt</p>
          <p slot="title">title solt 1</p>
          <p slot="title">title solt 2</p>
          <P slot="item" slot-scope="props">item slot-scope {{ props }}</P>
        </SlotDemo>
      </a-tab-pane>
      <a-tab-pane key="bigProps" tab="大属性">
        <BigProps
          :name="bigPropsName"
          :on-change="handleBigPropChange"
          :slot-default="getDefault()"
          :slot-title="getTitle()"
          :slot-scope-item="getItem"
        ></BigProps>
      </a-tab-pane>
    </a-tabs>
  </div>
</template>

<script>
import Props from './Props.vue'
import Event from './Event.vue'
import Slot from './Slot.vue'
import BigProps from './BigProps.vue'
export default {
  components: { 
    Props, 
    Event, 
    SlotDemo: Slot,
    BigProps 
  },
  data () {
    return {
      type: 'danger',
      name: '',
      bigPropsName: 'Hello world!'
    }
  },
  methods: {
    handlePropChange(val) {
      this.type = val
    },
    handleEventChange(val) {
      this.name = val
    },
    handleBigPropChange(val) {
      this.bigPropsName = val
    },
    getDefault() {
      return [this.$createElement('p', 'default slot')]
    },
    getTitle() {
      return [
        this.$createElement('p', 'title slot1'),
        this.$createElement('p', 'title slot2')
      ]
    },
    getItem(props) {
      return [
        this.$createElement('p', `item slot-scope ${JSON.stringify(props)}`)
      ]
    }
  }
}
</script>

<style lang='scss' scoped>
</style>