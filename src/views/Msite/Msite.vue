<template>
  <div>
    <mt-button type="default" @click="MessageBox">MessageBox</mt-button>
    <mt-button type="primary" @click="Toast">Toast</mt-button>
    <mt-button type="danger" @click="Indicator">Indicator</mt-button>
    <mt-button size="small">Toast</mt-button>
    <mt-button size="large">Toast</mt-button>
    <mt-button size="normal">Toast</mt-button>
    <mt-button disabled>Toast</mt-button>
    <mt-button plain>Toast</mt-button>
    <mt-button icon="back"></mt-button>
    <mt-button icon="more"></mt-button>

  </div>
</template>
<script>
import {Indicator, MessageBox, Toast} from 'mint-ui'

export default {
  methods: {
    MessageBox: function () {
      MessageBox('提示', '确认')
    },
    Toast: function () {
      let instance = Toast('提示信息')
      setTimeout(() => {
        instance.close()
      }, 2000)
    },
    Indicator: function () {
      Indicator.open({
        text: '加载中...',
        // spinnerType: 'fading-circle'
        spinnerType: 'triple-bounce'
      })
      setTimeout(() => {
        Indicator.close()
      }, 2000)
    }
  }
}
</script>
<style>

</style>
