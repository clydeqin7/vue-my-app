<template>
  <div id="app">
      {{msg}}
      <div>
        <input type="text" v-model="info"/>
        <button v-on:click="handleClick">添加</button>
      </div>
      <ul>
        <todo-item v-for="(item, index) in list" :key="index">
          <template v-slot:slotXXX="solotXXXProps">
            <span :style="{fontSize: '20px', color: solotXXXProps.checked ? 'red' : 'blue' }">{{item}}</span>
          </template>
        </todo-item>
      </ul>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem.vue'

export default {
  name: 'app',
  components: {
    TodoItem
  },
  data() {
    return {
      msg: 'hello world',
      info: '',
      list: []
    }
  },
  methods: {
    handleClick() {
      this.list.push(this.info)
      this.info = ''
    }
  }
}
</script>

<style>

</style>
