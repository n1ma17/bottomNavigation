<template>
  <div id="app">
    <!-- <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div> -->
    <router-view />
    <div id="bottom-nav">
      <BottomNav />
    </div>
  </div>
</template>
<script>
import BottomNav from "@/components/shared/BottomNavigation";
export default {
  components: {
    BottomNav,
  },
};
</script>
<style lang="scss">
:root {
  --white: #E0E1E9;
  --primary: #141B41;
  --seccondary: #E84855;
}
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
body {
  background-color: var(--white);
  display: flex;
  justify-content: center;
  align-items: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 100%;
  height: 100vh;
  color: var(--primary);
  position: relative;
 
  #bottom-nav {
    width: 95%;
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
  }
}
</style>
