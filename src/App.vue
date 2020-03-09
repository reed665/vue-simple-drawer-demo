<template>
  <div id="app">
    <header>
      <h1>Vue Simple Drawer Demo</h1>
    </header>

    <main>
      <button @click="openDrawer">
        Open Drawer
      </button>

      <AppDrawer :active="drawerIsActive">
        <div class="drawer-content">
          <h2>I am drawer</h2>

          <button @click="closeDrawer">
            Close
          </button>
        </div>
      </AppDrawer>
    </main>
  </div>
</template>

<script>
import { ref } from '@vue/composition-api';
import AppDrawer from './components/AppDrawer.vue';

export default {
  name: 'App',
  components: {
    AppDrawer,
  },

  setup() {
    const drawerIsActive = ref(false);

    const openDrawer = () => {
      drawerIsActive.value = true;
    };

    const closeDrawer = () => {
      drawerIsActive.value = false;
    };

    return {
      openDrawer,
      closeDrawer,
      drawerIsActive,
    };
  },

};
</script>

<style>
:root {
  --drawer-width: 640px;
}

body {
  background: lightgray;
  margin: 0;
}
</style>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  padding: 15px;
}

.drawer-content {
  padding: 15px;
}
</style>
