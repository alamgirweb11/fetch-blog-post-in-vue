<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="mt-3 mb-2">
    <b-row>
      <b-col cols="9">
        <b-row>
          <b-col
            v-for="(post, index) in posts"
            :key="index"
            cols="4"
          >
            <b-card
              :title="post.title"
              :img-src="post.thumbnail_img"
              img-alt="Image"
              img-top
              tag="article"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button variant="primary">
                <router-link
                  class="text-light"
                  :to="{name: 'postDetailsPage', params: {id:post.id}}"
                >
                  Read More...
                </router-link>
              </b-button>
            </b-card>
          </b-col>
        </b-row>
      </b-col>
      <b-col cols="3">
        <RightSidebar />
      </b-col>
    </b-row>
  </div>
</template>

<script>
import { BRow, BCol } from 'bootstrap-vue'
import RightSidebar from '@/components/RightSidebar.vue'
export default {
  components: {
    RightSidebar,
    BRow,
    BCol
  },
  data: function () {
    return {
      posts: []
    }
  },
  mounted () {
    this.allPosts()
  },
  methods: {
    allPosts () {
      const categoryPosts = this
      this.$http.get(`http://127.0.0.1:8000/api/category/${this.$route.params.slug}`)
        .then(function (response) {
          categoryPosts.posts = response.data
          console.log(response.data)
        })
        .catch(function (error) {
          console.log(error)
        })
    }
  }
}
</script>
