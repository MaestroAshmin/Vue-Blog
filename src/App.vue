<template>
  <div>
    <app-header></app-header>
    <router-view></router-view>
    <!-- <list-blogs></list-blogs> -->
  </div>
</template>

<script>
import addBlog from "./components/addBlog.vue";
import showBlog from "./components/showBlog.vue";
import listBlog from "./components/listBlogs.vue";
import header from "./components/header.vue";

export default {
  components: {
    "add-blog": addBlog,
    "show-blog": showBlog,
    "list-blogs": listBlog,
    "app-header": header
  },
  data() {
    return {};
  },
  methods: {}
};
</script>

<style>
body {
  margin: 0;
}
</style>
