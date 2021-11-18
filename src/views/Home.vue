<template>
  <div>
    <div class="container">
      <div class="text-center">
        <div class="center">
          <Avatar size="300" home="true" />
        </div>
        <h1><a  class="main-header" href="#/projects">{{ config.name }}</a></h1>
        <h4 style="color: #666666"><a class="main-head-user" href="#/about">{{ config.username }}</a></h4>
        <p class="main-head-para">{{ config.description }}</p>
      </div>
      <h2>Latest Posts</h2>
      <hr/>
      <div class="grid-3_xs-1_sm-2_md-2">
        <div
          :key="index"
          v-for="(post, index) in posts.slice(Math.max(posts.length - 6, 0)).reverse()"
          class="col"
        >
          <PostCard :post="post" class="center" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Posts from '@/../posts/data/posts.json'
import Config from '@/../posts/data/config.json'
import Avatar from '@/components/Avatar.vue'
import PostCard from '@/components/PostCard.vue'

export default {
  name: 'Home',
  components: {
    Avatar,
    PostCard
  },
  data: function () {
    return {
      posts: Posts.posts,
      config: Config.config
    }
  },
  mounted: function () {
    this.changeTitle('Home')
  }
}
</script>
