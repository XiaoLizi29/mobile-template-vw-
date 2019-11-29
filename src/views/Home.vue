<template>
  <div class="home">
    <van-action-sheet v-model="show" :actions="actions" @select="onSelect" />
    <van-button plain type="info">朴素按钮</van-button>
  </div>
</template>

<script>
import { ActionSheet, Toast, Button } from 'vant'
export default {
  name: 'home',
  components: {
    [ActionSheet.name]: ActionSheet,
    [Button.name]: Button,
  },
  data() {
    return {
      show: true,
      actions: [
        { name: '选项' },
        { name: '选项' },
        { name: '选项', subname: '描述信息' }
      ]
    }
  },

  methods: {
    onSelect(item) {
      // 默认情况下，点击选项时不会自动关闭菜单
      // 可以通过 close-on-click-action 属性开启自动关闭
      this.show = false
      Toast(item.name)
    }
  }
}
</script>

<style lang="scss" scoped>
</style>
