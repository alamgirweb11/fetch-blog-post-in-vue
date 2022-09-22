<template lang="">
  <div>
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
          <router-link :to="{name: 'categoryPosts', params: { slug: category.slug}}">
            {{ category.name }}
          </router-link>
        </b-list-group-item>
      </b-list-group>
    </b-card>
  </div>
</template>
<script>
export default {
  data () {
    return {
      categories: []
    }
  },
  mounted () {
    this.allCategories()
  },
  methods: {
    allCategories () {
      const fetchAllCategories = this
      this.$http.get('http://127.0.0.1:8000/api/categories')
        .then(function (response) {
          fetchAllCategories.categories = response.data
          console.log(response.data)
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
