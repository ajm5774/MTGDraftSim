<template>
  <el-container>
    <el-aside width="auto">
      <el-menu :collapse="!sidebarOpened" class="sidebar">
        <el-button @click="sidebarOpened = !sidebarOpened"
          size="mini"
          class="sidebar__collapse-button"
          :class="{ 'sidebar__collapse-button--opened': sidebarOpened }">
          <i class="el-icon-d-arrow-right" />
        </el-button>
        <el-menu-item index="index">
          <i class="material-icons">home</i>
          <span slot="title">Home</span>
        </el-menu-item>
      </el-menu>
    </el-aside>
    <el-container>
      <div class="content">
        <nuxt/>
      </div>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data() {
    return {
      sidebarOpened: false,
    };
  },
};
</script>

<style lang="scss" scoped>
  @import '~styles/variables.scss';

  .sidebar {
    background-color: $sideBarColor;
    height: 100%;
    width: $sideBarWidthClosed;
    &:not(.el-menu--collapse) {
      width: $sideBarWidthOpen;
    }

    &__collapse-button {
      width: 100%;
      border-radius: 0;
      text-align: right;
      border-right: 0;
      border-left: 0;
      border-top: 0;
      background-color: $sideBarColor;
    }
  }

  .content {
    padding: 20px;
    width: 100%;
    height: 100vh;
  }
</style>
