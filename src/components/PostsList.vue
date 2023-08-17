<script>
import axios from "axios";
import PostCard from "./PostCard.vue";

export default {
  components: {
    PostCard,
  },
  data() {
    return {
      arrPosts: [],
    };
  },
  methods: {
    getPosts() {
      axios
        .get("http://localhost:8000/api/posts", {
          params: {
            // page: this.currentPage,
            // q: new URLSearchParams(window.location.search).get("q"),
          },
        })
        .then((response) => {
          this.arrPosts = response.data.results.data;
          //   this.nPages = response.data.results.last_page;
        });
    },
  },
  created() {
    // richiesta dati al server
    this.getPosts();
  },
};
</script>

<template>
  <h1>Posts List</h1>
  <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 g-4 mb-5">
    <div class="col" v-for="post in arrPosts" :key="post.id">
      <PostCard :objPost="post" />
    </div>
  </div>
</template>

<style></style>
