<template>
  <div
    class="app-drawer"
    :class="{ 'active': active }"
  >
    <div
      v-if="active"
      class="drawer-inner"
    >
      <slot />
    </div>
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
  width: var(--drawer-width);
  transform: translateX(var(--drawer-width));
  transition: transform .3s ease-in-out;
}

.active {
  transform: translateX(0);
}
</style>
