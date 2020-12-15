<template>
  <div>
    <el-menu
      :default-active="activeIndex2"
      id="my-nav"
      mode="horizontal"
      @select="handleSelect"
      router
    >
      <el-menu-item index="/">
        <!-- <img src="../assets/chemicon-icon.png" alt="" class="brand-pic" /> -->
        aa
      </el-menu-item>
      <template v-for="nav in navObjList">
        <el-submenu
          :index="nav.url"
          v-if="nav.children.length != 0"
          :key="nav.navId"
        >
          <template slot="title">{{ nav.navName }}</template>
          <el-menu-item
            v-for="child in nav.children"
            :key="child.navId"
            :index="child.url"
            >{{ child.navName }}</el-menu-item
          >
        </el-submenu>
        <el-menu-item :index="nav.url" v-else :key="nav.navId">{{
          nav.navName
        }}</el-menu-item>
      </template>
    </el-menu>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: "1",
      activeIndex2: "1",
      navObjList: [
        {
          navId: 1,
          navName: "Home",
          url: "",
          children: [],
        },
        {
          navId: 2,
          navName: "Product",
          url: "",
          children: [
            {
              navId: 4,
              navName: "software",
              url: "/editor",
              children: [],
            },
          ],
        },
        {
          navId: 3,
          navName: "About",
          url: "/about",
          children: []
        },
      ],
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      console.log(key, keyPath);
    },
  },
};
</script>

<style>
.brand-pic {
  height: 60px;
}
</style>