<template>
  <div v-theme:column="'narrow'" id="show-blogs">
    <h1>List Blog Title:</h1>
    <input type="text" v-model="search" placeholder="searchbox" />
    <div v-for="blog in filteredBlogs" class="single-blog">
      <h2 v-rainbow>{{blog.title | to-uppercase}}</h2>
    </div>
  </div>
</template>

<script>
import searchmixin from "../mixins/searchmixin";
export default {
  data() {
    return {
      blogs: [],
      search: ""
    };
  },
  methods: {},
  created() {
    this.$http
      .get("http://jsonplaceholder.typicode.com/posts")
      .then(function(data) {
        this.blogs = data.body.slice(0, 10);
      });
  },
  filters: {
    "to-uppercase": function(value) {
      return value.toUpperCase();
    }
  },
  directives: {
    rainbow: {
      bind(el, binding, vnode) {
        el.style.color =
          "#" +
          Math.random()
            .toString()
            .slice(2, 8);
      }
    }
  },
  mixins: [searchmixin]
  // toUppercase(value) {
  //   return value.toUppercase();
  // }
};
</script>

<style>
#show-blogs {
  max-width: 800px;
  margin: 0px auto;
}
.single-blog {
  padding: 20px;
  margin: 20px 0;
  box-sizing: border-box;
  background: #eee;
}
</style>