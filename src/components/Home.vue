<template>
  <el-container>
    <el-header>
      M&oacute;dulo ajustes
      <el-button
        type="info"
        icon="el-icon-back"
        circle
        @click="logout"
        title="logout"
      ></el-button>
    </el-header>
    <el-container>
      <el-aside width="200px">
        <el-menu :default-openeds="['1', '3']">
          <el-submenu index="1">
            <template slot="title"
              ><i class="el-icon-menu"></i>Men&uacute;</template
            >
            <el-submenu index="1-4">
              <template slot="title">Usuarios</template>
              <el-menu-item index="1-4-1">Mantenedor</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
      </el-aside>
      <el-main>Contenido</el-main>
    </el-container>
  </el-container>
</template>
<script>
//import Firebase from "firebase/app";
export default {
  data() {
    return {};
  },
  methods: {
    logout() {
      this.$router.push("login");
    },
  },
};
</script>