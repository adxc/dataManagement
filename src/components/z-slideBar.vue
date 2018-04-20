<template>
  <div class="g-sd">
    <el-radio-group v-model="isCollapse" >
      <el-radio-button :label="!isCollapse" class="nav-switch"><img src="../assets/slider/sidebar-toggler.jpg" alt=""></el-radio-button>
    </el-radio-group>
    <el-menu default-active="2"
             class="el-menu-vertical-demo"
             @open="handleOpen"
             @close="handleClose"
             background-color="#545c64"
             text-color="#fff"
             active-text-color="#ffd04b"
             :collapse="isCollapse">
      <el-menu-item index="1" class="f-taj">
        <i class="iconfont icon-dashbord "></i>
        <span slot="title" class="nav-title">应用状况</span>
      </el-menu-item>
      <el-menu-item index="2" class="f-taj">
        <i class="iconfont icon-shujudongtai "></i>
        <span slot="title" class="nav-title">视图</span>
      </el-menu-item>
      <el-submenu index="3" class="f-taj">
        <template slot="title">
          <i class="el-icon-menu"></i>
          <span slot="title" class="nav-title">预警布控</span>
        </template>
        <el-menu-item-group>
          <span slot="title">分组一</span>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="1-3">选项3</el-menu-item>
        </el-menu-item-group>
        <el-submenu index="1-4">
          <span slot="title">选项4</span>
          <el-menu-item index="1-4-1">选项1</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-submenu index="4" class="f-taj">
        <template slot="title">
          <i class="iconfont icon-icon--1 "></i>
          <span slot="title" class="nav-title">档案库</span>
        </template>
        <el-menu-item-group>
          <span slot="title">分组一</span>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="1-3">选项3</el-menu-item>
        </el-menu-item-group>
        <el-submenu index="1-4">
          <span slot="title">选项4</span>
          <el-menu-item index="1-4-1">选项1</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-menu-item index="5" class="f-taj">
        <i class="el-icon-search"></i>
        <span slot="title" class="nav-title">一键搜</span>
      </el-menu-item>
      <el-submenu index="6" class="f-taj">
        <template slot="title">
          <i class="el-icon-document"></i>
          <span slot="title" class="nav-title">数据分析</span>
        </template>
        <el-menu-item-group>
          <span slot="title">分组一</span>
          <el-menu-item index="1-1">选项1</el-menu-item>
          <el-menu-item index="1-2">选项2</el-menu-item>
        </el-menu-item-group>
        <el-menu-item-group title="分组2">
          <el-menu-item index="1-3">选项3</el-menu-item>
        </el-menu-item-group>
        <el-submenu index="1-4">
          <span slot="title">选项4</span>
          <el-menu-item index="1-4-1">选项1</el-menu-item>
        </el-submenu>
      </el-submenu>
      <el-menu-item index="7" class="f-taj">
        <i class="el-icon-edit-outline"></i>
        <span slot="title" class="nav-title">业务考核</span>
      </el-menu-item>
    </el-menu>
  </div>
</template>

<script>
export default {
  name: 'z-slideBar',
  data () {
    return {
      isCollapse: false
    }
  },
  methods: {
    handleOpen (key, keyPath) {
      console.log(key, keyPath)
    },
    handleClose (key, keyPath) {
      console.log(key, keyPath)
    }
  }
}
</script>

<style lang='postcss'>
  .g-sd{
    display: flex;
    flex-direction: column;
    .iconfont{
      margin-right: 5px;
      width: 24px;
      text-align: center;
      font-size: 16px;
      vertical-align: middle;
      display: inline-block;
    }
  }
  .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    flex: auto;
  }
  .el-menu--collapse{
    flex: auto;
    width: 70px;
  }
  .nav-title {
    text-align: justify;
    text-align-last: justify;
    display: inline-block;
    width: 56px;
  }
  .el-radio-group{
    background: #545c64;
    border-right: solid 1px #e6e6e6;
    text-align: right;
    .nav-switch{
      .el-radio-button__inner{
        background: #545c64;
        border: none;
      }
    }
  }
  </style>
