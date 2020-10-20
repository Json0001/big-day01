<template>
  <div class="home">
  <el-container>
  <el-aside width="">
    <!-- 侧边栏 -->

<el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse">
  <!-- 1 -->
  <el-menu-item index="2">
    <i class="el-icon-s-claim"></i>
    <span slot="title">管理首页</span>
  </el-menu-item>

  <el-submenu index="1">
    <template slot="title">
      <i class="el-icon-s-custom"></i>
      <span slot="title">学员管理</span>
    </template>
    <el-menu-item-group>
      <span slot="title"></span>
      <el-menu-item index="1-1">学员项目管理</el-menu-item>
      <el-menu-item index="1-2">学员资料</el-menu-item>
    </el-menu-item-group>
     <el-menu-item-group>
      <el-menu-item index="1-3">学员宿舍</el-menu-item>
    </el-menu-item-group>
  </el-submenu>
  <!-- 2 -->
  
  <!-- 3 -->
  
  <!-- 4 -->
  <el-menu-item index="4">
    <i class="el-icon-mouse"></i>
    <span slot="title">考勤管理</span>
  </el-menu-item>
  <el-menu-item index="4">
    <i class="el-icon-loading"></i>
    <span slot="title">数据统计</span>
  </el-menu-item>
  <el-menu-item index="4">
    <i class="el-icon-chat-dot-round"></i>
    <span slot="title">我的中心</span>
  </el-menu-item>
</el-menu>
  </el-aside>
  <!-- 头部 -->
  <el-container>
    <el-header>
      <el-button icon="el-icon-s-fold" @click="isCollapse=!isCollapse"></el-button>
      <span>千锋管理系统</span>
      
 <div>
   <img src="" alt="">
   欢迎您：
   <a href="">退出</a>
 </div>
      
       
      
    </el-header>
    <!-- 主体 -->
    <el-main>Main</el-main>
  </el-container>
</el-container>
  </div>
</template>
<script>
//侧边栏操作
  export default {
    data() {
      return {
        isCollapse: true
      };
    },
    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>
<style scoped>
/* 侧边栏 */
.el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }
  .el-menu{
    margin-top: 60px;
  }
/* 整体布局 */
  .el-header{
    background-color: #ccc;
    color:black;
    text-align: center;
    line-height: 60px;
    display: flex;
    justify-content: space-between;
  }
  .el-header .el-button{
    background: #ccc;
    border: 0;
    font-size: 45px;
  }
  .el-aside {
    background-color: #aaa;
    color:black;
    text-align: center;
    line-height: 200px;
  }
  
  .el-main {
    background-color: #E9EEF3;
    color: black;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  
  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }
  
  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
