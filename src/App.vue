<template>
  <div>
    <show-blog></show-blog>
    <list-blogs></list-blogs>
  </div>
</template>

<script>
import addBlog from "./components/addBlog.vue";
import showBlog from "./components/showBlog.vue";
import listBlog from "./components/listBlogs.vue";

export default {
  components: {
    "add-blog": addBlog,
    "show-blog": showBlog,
    "list-blogs": listBlog
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
