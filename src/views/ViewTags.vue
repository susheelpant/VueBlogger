<template>
  <div class="container">
    <h1 class="text-center">Tags</h1>
    <hr />
    <div class="grid-3_xs-1_sm-2_md-2">
      <div
        v-for="(tag, index) in tags"
        :key="index"
        class="col"
      >
        <router-link :to="`/tags/${tag.name}`">
          <vs-card
            type="3"
            class="center"
          >
            <template #title>
              <h3>{{ tag.name }}</h3>
            </template>
            <template #text>
              <p>
                {{ tag.posts.length }} post{{ `${tag.posts.length !== 1 ? "s" : ""}` }}
              </p>
            </template>
          </vs-card>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ViewTags',
  mounted: function () {
    this.changeTitle('Tags')
  }
}
</script>
