<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="mt-3 mb-2">
    <b-row class="mb-2">
      <b-form-group
        id="input-group-3"
        label-for="input-3"
      >
        <b-form-select
          id="input-3"
          v-model="form.category"
          label="Filter:"
          class="form-control"
          :options="categories"
          required
        />
      </b-form-group>
    </b-row>
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
                  :to="{name: 'posDetails', params: {id:post.id}}"
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
import { BRow, BCol, BFormGroup, BFormSelect } from 'bootstrap-vue'
import RightSidebar from '@/components/RightSidebar.vue'
export default {
  components: {
    RightSidebar,
    BRow,
    BCol,
    BFormGroup,
    BFormSelect
  },
  data: function () {
    return {
      form: {
        category: null
      },
      posts: [],
      categories: [
        { text: 'Filter Post', value: null },
        'Category-1',
        'Category-2',
        'Category-3',
        'Category-4'
      ]
    }
  },
  mounted () {
    this.allPosts()
  },
  methods: {
    allPosts () {
      const fetchAllPosts = this
      this.$http.get('http://127.0.0.1:8000/api/posts')
        .then(function (response) {
          fetchAllPosts.posts = response.data
          console.log(response.data)
        })
        .catch(function (error) {
          console.log(error)
        })
    }
  }
}
</script>
