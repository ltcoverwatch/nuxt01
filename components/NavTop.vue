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
      <template v-for="nav in pcNavList">
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
    <p>{{ screenWidth }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      screenWidth: 0,
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
          children: [],
        },
      ],
    };
  },
  computed: {
    pcNavList: function () {
      // console.log(this.pcNavList);
      return this.screenWidth >= 768 ? this.navObjList : [];
    },
    mobileNavList: function () {
      return this.screenWidth < 768 ? this.navObjList : [];
    },
  },
  watch: {
    screenWidth(newValue) {
      // 为了避免频繁触发resize函数导致页面卡顿，使用定时器
      if (!this.timer) {
        // 一旦监听到的screenWidth值改变，就将其重新赋给data里的screenWidth
        this.screenWidth = newValue;
        this.timer = true;
        setTimeout(() => {
          //console.log(this.screenWidth);
          this.timer = false;
        }, 400);
      }
    },
  },
  created() {},
  mounted() {
    this.screenWidth = document.body.clientWidth;
    window.onresize = () => {
      this.screenWidth = document.body.clientWidth;
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
