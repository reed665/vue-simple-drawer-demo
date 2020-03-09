<template>
  <div
    v-if="active"
    class="app-drawer"
    :class="{ 'active': active }"
  >
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    active: {
      type: Boolean,
      default: false,
    },
  },

};
</script>

<style scoped>
.app-drawer {
  background: white;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  width: 60%;
}

</style>
