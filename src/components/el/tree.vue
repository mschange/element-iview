<template>
	<!--左侧菜单组件-->
  <el-menu
    default-active="0"
    class="el-menu-vertical-demo"
    @select="menuSelected"
    background-color="#545c64"
    text-color="#fff"
    active-text-color="#ffd04b">
    <nav-menu :navMenus="menu"></nav-menu>
  </el-menu>
</template>
 
<script>
	import NavMenu from './SliderMenu.vue'
	export default{
		data() {
      return {
        // activeIndex: "1",
        // activeIndex2: "1", // 路由只需设置最深一级菜单的即可
        menu: [
          // 三级菜单
          {
            name: "菜单三",
            route: "/",
            children: [
              {
                name: "菜单三__1",
                route: "/",
                children: [
                  {
                    name: "菜单三__1-1",
                    route: "/console/one"
                  },
                  {
                    name: "菜单三__1-2",
                    route: "/console/two"
                  }
                ]
              }
            ]
          },
          {
            name: "菜单二",
            route: "/",
            children: [
              {
                name: "菜单二__1",
                route: "/second/one"
              },
              {
                name: "菜单二__2",
                route: "/second/two"
              }
            ]
          },
          // 一级菜单
          {
            name: "菜单一",
            route: "/third"
          }
        ]
      };
    },
		components:{
			NavMenu
		},
		methods:{
			menuSelected(index,indexPath){
				console.log('当前绑定的index值',index)
				console.log('当前绑定的index与path值',indexPath)
			}
		}
	}
</script>
 
<style>
</style>