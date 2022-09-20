<template lang="">
  <div class="mt-3 mb-2">
    <b-row>
      <b-col cols="9">
        <h5>Title Tag</h5>
        <img
          src="https://via.placeholder.com/350x150"
          alt=""
          srcset=""
        >
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur soluta excepturi dignissimos provident illo tempore amet perspiciatis, facilis ea odio! Placeat, reiciendis eaque! Voluptatibus, modi. Ipsa quis iste aut delectus reiciendis. Praesentium corrupti ullam, molestiae rerum voluptates porro qui accusantium quas explicabo laboriosam accusamus autem. Reiciendis voluptate obcaecati, iste officiis laborum dicta magni facilis asperiores vero repellendus perferendis perspiciatis, aliquid rem dolorem! Dolorum accusamus ullam fugiat aperiam saepe inventore tempore rerum, aliquam odit iure? Fugit impedit facilis esse nulla nostrum quasi, recusandae ex perspiciatis nobis repellat reiciendis illum, nisi amet. Enim reiciendis rem earum ipsa vel facilis cumque, cum nam.</p>
      </b-col>
      <b-col cols="3">
        <RightSidebar />
      </b-col>
    </b-row>
  </div>
</template>
<script>
import RightSidebar from '../components/RightSidebar.vue'
import { BRow, BCol } from 'bootstrap-vue'
export default {
  data () {
    return {
      post: []
    }
  },
  components: {
    RightSidebar,
    BRow,
    BCol
  },
  mounted () {
    this.getSinglePost()
  },
  methods: {
    getSinglePost (slug) {
      // const singlePost = this
      // this.$http.get('http://127.0.0.1:8000/api/post/:slug')
      //   .then(function (response) {
      //     singlePost.post = response.data
      //     console.log(response.data)
      //   })
      //   .catch(function (error) {
      //     console.log(error)
      //   })
    }
  }
}
</script>
<style lang="">

</style>
