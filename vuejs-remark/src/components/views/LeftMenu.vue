<template>
  <el-menu  v-show="!collapsed" class="el-menu-vertical-demo">
    <template v-for="(rootitem,index) in leftMenuList" :index="index">
       <el-submenu  class="submenu">
         <template slot="title">{{rootitem.item}}</template>
         <template v-for="subitems in rootitem.children">
           <el-menu-item >{{subitems.item}}</el-menu-item>
         </template>

       </el-submenu>
    </template>

  </el-menu>
</template>
<script>
  export default {
    data() {
      return {
        leftMenuList: [
          {id: '1', item: 'Menu', children: [{id: '11', item: 'Menu1-1'}, {id: '12', item: 'Menu1-2'}]},
          {id: '2', item: 'Menu', children: [{id: '21', item: 'Menu2-1'}, {id: '22', item: 'Menu2-2'}]}
        ]
      }
    },
    methods: {}
  }
</script>
