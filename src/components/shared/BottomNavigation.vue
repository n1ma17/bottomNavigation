<template>
  <div class="bottom-nav">
    <Menu :items="menuList" />
  </div>
</template>

<script>
import Menu from "@/components/bottom-navigation/Menu.vue";
export default {
  name: "BottomNavigation",
  components: {
    Menu,
  },
  data() {
    return {
      menuList: [
        {
          title: "Home",
          route: "/",
          icon: "home-outline",
          isActive:true
        },
        {
          title: "Profile",
          route: "/profile",
          icon: "people-outline",
          isActive:false
        },

        {
          title: "About",
          route: "/about",
          icon: "alert-circle-outline",
          isActive:false
        },
        {
          title: "Cart",
          route: "/cart",
          icon: "journal-outline",
          isActive:false
        },
        {
          title: "Menu",
          route: "/cart",
          icon: "apps-outline",
          isActive:false
        }
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.bottom-nav {
  background-color: var(--primary);
  width: 100%;
  height: 70px;
  border-radius: 10px;
  display: flex;
    align-items: center;
    justify-content: center;
}
</style>