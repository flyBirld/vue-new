<template>
   <div class='frame'>
      <component :is='(layoutData.value || "regular") + "-layout"'></component>
   </div>
</template>
<script>
import { mapGetters } from 'vuex'
export default {
  name: 'frame',
  data: function () {
    return {
    }
  },
  computed: {
    ...mapGetters({
      layoutData: 'sysLayoutName/data'
    })
  },
  mounted: function () {
    // this.$route对象在顶级视图中有一定的延迟，这里使用 vuex 配合路由导航守卫触发变更
  },
  methods: {
  },
  components: {
    RegularLayout: () => import('./regularLayout'),
    NoLayout: () => import('./noLayout')
  }
}
</script>
<style>
.frame {
  height: 100%;
  width: 100%;
}
</style>
