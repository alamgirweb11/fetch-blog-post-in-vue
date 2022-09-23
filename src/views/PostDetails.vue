<template>
  <div class="mt-3 mb-2">
    <b-row>
      <b-col cols="12">
        <h5>{{ post.title }}</h5>
        <img
          :src="post.thumbnail_img"
          alt=""
          srcset=""
        >
        <p>{{ post.description }}</p>
      </b-col>
    </b-row>
  </div>
</template>
<script>
import { BRow, BCol } from 'bootstrap-vue'
export default {
  components: {
    BRow,
    BCol
  },
  data () {
    return {
      post: []
    }
  },
  mounted () {
    this.getSinglePost()
  },
  methods: {
    getSinglePost () {
      const singlePost = this
      // eslint-disable-next-line no-undef
      this.$http.get(`http://127.0.0.1:8000/api/post/${this.$route.params.id}`)
        .then(function (response) {
          singlePost.post = response.data
        })
        .catch(function (error) {
          console.log(error)
        })
    }
  }
}
</script>
<style lang="">

</style>
