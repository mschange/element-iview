<template>
  <div class="side-menu-wrapper">
    <Menu theme="dark" :open-names="['1']" accordion @on-select="handleSelect" width="100">
      <template v-for="item in leftMenus">
        <re-submenu v-if="item.children && item.children.length > 0" :parent="item" :key="item.alias"></re-submenu>
        <Submenu :name="item.name" v-else  :key="item.alias">
          <template slot="title">
              <i :class="item.icon"></i>
              {{ item.alias }}
          </template>
        </Submenu>
      </template>
    </Menu>
  </div>
</template>

<script>
  import ReSubmenu from "./re-submenu.vue";
  export default {
    name: "side_menu",
    components: {
      're-submenu': ReSubmenu
    },
    props: {
      
    },
    data() {
      return {
        leftMenus: [
          {
            "id": 1,
            "parentMenuId": 0,
            "name": "systemManage",
            "icon": "el-icon-message\r\n",
            "alias": "系统管理",
            "state": "ENABLE",
            "sort": 0,
            "value": null,
            "type": "NONE",
            "discription": "用于系统管理的菜单",
            "createUserId": 1,
            children: [
              {
                "id": 3,
                "parentMenuId": 1,
                "name": "authManage",
                "icon": "el-icon-loading",
                "alias": "权限管理",
                "state": "ENABLE",
                "sort": 0,
                "value": "/system/auth",
                "type": "LINK",
                "discription": "用于权限管理的菜单",
                "createUserId": 1
              },
              {
                "id": 4,
                "parentMenuId": 1,
                "name": "roleManage",
                "icon": "el-icon-bell",
                "alias": "角色管理",
                "state": "ENABLE",
                "sort": 1,
                "value": "/system/role",
                "type": "LINK",
                "discription": "用于角色管理的菜单",
                "createUserId": 1
              }
            ]                   
          },
          {
            "id": 2,
            "parentMenuId": 1,
            "name": "menuManage",
            "icon": "el-icon-edit",
            "alias": "菜单管理",
            "state": "ENABLE",
            "sort": 2,
            "value": "/system/menu",
            "type": "LINK",
            "discription": "用于菜单管理的菜单",
            "createUserId": 1,
            children: [
              {
                "id": 5,
                "parentMenuId": 1,
                "name": "groupManage",
                "icon": "el-icon-mobile-phone\r\n",
                "alias": "分组管理",
                "state": "ENABLE",
                "sort": 3,
                "value": "/system/group",
                "type": "LINK",
                "discription": "用于分组管理的菜单",
                "createUserId": 1
              },
              {
                "id": 6,
                "parentMenuId": 0,
                "name": "userManage",
                "icon": "el-icon-news",
                "alias": "用户管理",
                "state": "ENABLE",
                "sort": 1,
                "value": null,
                "type": "NONE",
                "discription": "用于用户管理的菜单",
                "createUserId": 1,
                children: [
                  {
                    "id": 7,
                    "parentMenuId": 6,
                    "name": "accountManage",
                    "icon": "el-icon-phone-outline\r\n",
                    "alias": "帐号管理",
                    "state": "ENABLE",
                    "sort": 0,
                    "value": "",
                    "type": "NONE",
                    "discription": "用于帐号管理的菜单",
                    "createUserId": 1,
                    children: [
                      {
                        "id": 14,
                        "parentMenuId": 7,
                        "name": "emailManage",
                        "icon": "el-icon-sold-out\r\n",
                        "alias": "邮箱管理",
                        "state": "ENABLE",
                        "sort": 0,
                        "value": "/content/email",
                        "type": "LINK",
                        "discription": "用于邮箱管理的菜单",
                        "createUserId": 1
                      }
                    ]
                  },
                  {
                    "id": 13,
                    "parentMenuId": 7,
                    "name": "passManage",
                    "icon": "el-icon-service\r\n",
                    "alias": "密码管理",
                    "state": "ENABLE",
                    "sort": 1,
                    "value": "/content/pass",
                    "type": "LINK",
                    "discription": "用于密码管理的菜单",
                    "createUserId": 1
                  }
                ]
              }
            ]
          }
        ]
      };
    },
    methods: {
      handleSelect(name) {
        console.log(name, '----')
      }
    },
  };
</script>