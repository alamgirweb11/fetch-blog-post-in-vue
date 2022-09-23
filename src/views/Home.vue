<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="mt-3 mb-2">
    <b-row class="mb-2">
      <b-form-group>
        <b-form-input
          v-model="searchInput"
          class="form-control"
          placeholder="Search..."
          required
          @keyup="submitSearchData"
        />
      </b-form-group>
    </b-row>
    <b-row>
      <b-col cols="9">
        <b-row v-if="posts.length > 0">
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
                {{ post.description.substring(0,80)+"..." }}
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
        <b-row v-else>
          <b class="text-danger text-center">No Data Found!</b>
        </b-row>
      </b-col>
      <b-col cols="3">
        <b-card
          no-body
        >
          <template #header>
            <h4 class="mb-0">
              Categories
            </h4>
          </template>
          <b-list-group
            v-for="(category, index) in categories"
            :key="index"
            flush
          >
            <b-list-group-item>
              <b-list-group-item
                style="cursor: pointer"
                @click="categoryWisePost (category.id)"
              >
                {{ category.name }}
              </b-list-group-item>
            </b-list-group-item>
          </b-list-group>
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import { BRow, BCol, BFormGroup, BFormInput } from 'bootstrap-vue'
export default {
  components: {
    BRow,
    BCol,
    BFormGroup,
    BFormInput
  },
  data: function () {
    return {
      searchInput: '',
      posts: [],
      categories: [],
      manipulatePostData: []
    }
  },
  mounted () {
    this.allPosts()
    this.allCategories()
  },
  methods: {
    allPosts () {
      const fetchAllPosts = this
      this.$http.get('http://127.0.0.1:8000/api/posts')
        .then(function (response) {
          fetchAllPosts.posts = response.data
          fetchAllPosts.manipulatePostData = response.data
        })
        .catch(function (error) {
          console.log(error)
        })
    },
    allCategories () {
      const fetchAllCategories = this
      this.$http.get('http://127.0.0.1:8000/api/categories')
        .then(function (response) {
          fetchAllCategories.categories = response.data
        })
        .catch(function (error) {
          console.log(error)
        })
    },
    categoryWisePost (categoryId) {
      this.posts = this.manipulatePostData.filter(post => post.category_id === categoryId)
    },
    submitSearchData () {
      this.posts = this.manipulatePostData.filter(post => post.title.toLowerCase().includes(this.searchInput.toLowerCase()))
    }
  }
}
</script>
