<template>
  <div>
    <button @click="x">换肤</button>
    <button @click="changeFontsize('big')">大字</button>
    <button @click="changeFontsize('small')">小字</button>
    <button @click="changeFontsize('normal')">正常字</button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'ChangeThemeButton',
  inject:['themeName','changeTheme','changeFontsize'],
  methods:{
    x(){
      this.changeTheme()

    }
  }
}

</script>

<style lang="scss" scoped>

</style>