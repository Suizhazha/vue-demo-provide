<template>
  <div>
    Child1
    <ChangeThemeButton/>
  </div>
</template>

<script lang="ts">
import ChangeThemeButton from './ChangeThemeButton.vue';
export default {
  name: 'Child1',
  components: {ChangeThemeButton}
};
</script>

<style lang="scss" scoped>

</style>