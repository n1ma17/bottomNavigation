<template>
  <ul class="menu">
    <div class="menu__indicator" :style="style"></div>
    <li
      class="menu__list"
      :class="item.isActive ? 'active' : ''"
      v-for="(item, i) in items"
      :key="`bottom-nav-${i}`"
      @click="activeLink(item, i)"
    >
      <a class="menu__list__item">
        <span class="menu__list__item__icon">
          <ion-icon :name="item.icon"></ion-icon>
        </span>
        <span class="menu__list__item__text">{{ item.title }}</span>
      </a>
    </li>
  </ul>
</template>

<script>
export default {
  name: "BottomNavigationMenue",
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      style: "",
    };
  },
  methods: {
    activeLink(menuItem, i) {
      this.style = `transform: translateX(calc(70px * ${i})`;
      this.items.find((item) => item.isActive === true).isActive = false;
      this.items.find((item) => item.title === menuItem.title).isActive = true;
    },
  },
};
</script>

<style lang="scss" scoped>
.menu {
  width: 350px;
  height: 100%;
  list-style-type: none;
  display: flex;
  align-items: center;
  color: var(--white);

  &__list {
    width: 70px;
    height: 70px;
    position: relative;
    &__item {
      text-decoration: none;
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      width: 100%;
      font-weight: 500;
      text-align: center;
      &__icon {
        position: relative;
        display: block;
        line-height: 75px;
        font-size: 1.5em;
        text-align: center;
        color: var(--white);
        transition: 0.5s;
      }
      &__text {
        color: var(--white);
        font-weight: 400;
        position: absolute;
        font-size: 0.75em;
        letter-spacing: 0.05em;
        transition: 0.5s;
        opacity: 0;
        transform: translateY(20px);
      }
    }
  }
  &__indicator {
    padding: 0;
    position: absolute;
    top: -50%;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    border: 6px solid var(--white);
    background-color: var(--seccondary);
    transition: 0.5s;
    &::before {
      content: "";
      position: absolute;
      top: 50%;
      left: -22px;
      width: 20px;
      height: 20px;
      border-top-right-radius: 20px;
      box-shadow: 1px -10px 0 0 var(--white);
    }
    &::after {
      content: "";
      position: absolute;
      top: 50%;
      right: -22px;
      width: 20px;
      height: 20px;
      border-top-left-radius: 20px;
      box-shadow: -1px -10px 0 0 var(--white);
    }
  }
}
.menu li.active ~ .menu__indicator {
  transform: translateX(calc(70px * 3));
}
.menu li.active a .menu__list__item__text {
  opacity: 1;
  transform: translateY(10px);
}
.menu li.active a .menu__list__item__icon {
  transform: translateY(-34px);
  color: var(--primary);
}
</style>