<template>
  <div>
    <label>Default</label>
    <br>
    <sysbar/>
    <label>With logo</label>
    <br>
    <sysbar product="Product">
      <img :src="logo" slot="logo" style="height: 40px; self-align: center;">
    </sysbar>
  </div>
</template>

<script>
import Sysbar from '@/components/Sysbar'
import logo from '@/assets/logo.png'

export default {
  components: { Sysbar },
  data() {
    return {
      logo
    }
  }
}
</script>

<style>
</style>
