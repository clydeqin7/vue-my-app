
<template>
  <div>
    <a-tabs>
      <a-tab-pane key="Computed" tab="计算属性">
        <Computed />
      </a-tab-pane>
      <a-tab-pane key="Watch" tab="侦听器">
        <Watch />
      </a-tab-pane>
      <a-tab-pane key="vs" tab="计算属性 vs 侦听器">
        <Computed1 />
        <br />
        <Watch1 />
      </a-tab-pane>
      <a-tab-pane key="Watch1_pro" tab="防抖版">
        <WatchPro />
      </a-tab-pane>
      <a-tab-pane key="WatchMy" tab="my防抖版">
        <WatchMy />
      </a-tab-pane>
    </a-tabs>
  </div>
</template>
<script>
import Computed from "./Computed";
import Computed1 from "./Computed1";
import Watch from "./Watch";
import Watch1 from "./Watch1";
import WatchPro from "./Watch1_pro";
import WatchMy from './WatchMy.vue';
export default {
  components: {
    Computed,
    Computed1,
    Watch,
    Watch1,
    WatchPro,
    WatchMy
  }
};
</script>