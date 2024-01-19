<template>
  <div id="app">
    <el-container>
      <el-header style="background-color: #687179">
        <img src="@/assets/logo.png" alt="" style="width: 40px; position: relative; top: 10px;">
        <span style="font-size: 20px; margin-left: 15px; color: white">手拉手带小白做毕设</span>
      </el-header>
    </el-container>

    <el-container>
      <el-aside style="overflow: hidden; min-height: 100vh; background-color: #545c64; width: 250px">
        <!--        overflow: hidden;：这个属性设置为 hidden 表示如果内容超出了元素的盒子边界，它将被隐藏，不会出现滚动条。-->
        <!--        min-height: 100vh;：这里的 vh 单位是视口高度的百分比。100vh 表示 el-aside 的最小高度将与视口的高度一致，确保侧边栏在垂直方向上至少占满整个视口的高度。-->
        <!--        background-color: #545c64;：设置背景颜色为深灰色，#545c64 是该颜色的十六进制代码。-->
        <!--        width: 250px：设置 el-aside 组件的宽度为 250 像素。-->

        <el-menu :default-active="$route.path" router class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" background-color="#545c64" text-color="#fff" active-text-color="#ffd04b">

          <el-menu-item index="/">
            <i class="el-icon-s-platform"></i>
            <span slot="title">系统首页</span>
          </el-menu-item>


          <el-submenu index="2">
            <template slot="title">
<!--              <i> 标签通常用于表示斜体文本，但在现代的Web开发实践中，<i> 标签经常被用作图标字体的容器。-->
              <i class="el-icon-user-solid"></i>
              <span>信息管理</span>
            </template>

            <el-menu-item-group>
              <el-menu-item index="/admin">管理员信息</el-menu-item>
              <el-menu-item index="1-2">用户信息</el-menu-item>
            </el-menu-item-group>


          </el-submenu>




        </el-menu>


      </el-aside>
      <el-main>
          <router-view></router-view>
      </el-main>
    </el-container>

    <router-view/>
  </div>
</template>