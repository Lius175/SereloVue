<template>
  <router-view />
</template>

<script>


export default {


  data() {
    return {
      sidebaropen: true,
    }
  },

  methods: {
    toggleSidebar() {
      const sidebar = this.sidebaropen;
      if (sidebar == true) {
        this.sidebaropen = false;
      } else if (sidebar == false) {
        this.sidebaropen = true;
      }

    }
  }
};
</script>

<style>
.header {
  width: calc(100%-200px);
  align-items: right;
}

.content {
  width: calc(100%-200px);
}



body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>