<template>
  <div class="index p-80">
    {{ state.msg }}
    <div class="btn">
      <nut-button type="primary" @click="handleClick('text', state.msg2, true)">点我</nut-button>
    </div>
    <nut-toast :msg="state.msg" v-model:visible="state.show" :type="state.type" :cover="state.cover" />
  </div>
</template>
<script lang="ts" setup>
const state = ref({
  msg: '欢迎使用 NutUI3.0 开发小程序',
  msg2: '你成功了～',
  type: 'text',
  show: false,
  cover: false,
})
const handleClick = (type, msg, cover = false) => {
  state.value.show = true
  state.value.msg2 = msg
  state.value.type = type
  state.value.cover = cover
}
</script>

<style lang="scss">
.index {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
