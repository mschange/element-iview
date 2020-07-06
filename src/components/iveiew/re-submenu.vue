<template>
  <div class="submenuList ys-MenuList">
      <Submenu :name="`${parent.alias}`">
        <template slot="title">
          <i :class="parent.icon"></i>
          <span class="menuName">{{parent.alias}}</span>
        </template>
        <div>
          <template v-for="item in parent.children">
            <re-submenu v-if="item.children && item.children.length > 0" :parent="item" :key="item.alias"></re-submenu>
            <menu-item :name="item.name" v-else  :key="item.alias"><span class="menuName">{{ item.alias }}</span></menu-item>
          </template>
        </div>
      </Submenu>
  </div>

</template>

<script>
  export default {
    name: 'ReSubmenu',
    props: {
      parent: {
        type: Object,
        default: () => ({})
      },
      mounted() {
      },
    }
  }
</script>