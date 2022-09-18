<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="mt-3 mb-2">
    <b-row class="mb-2">
      <b-form-group id="input-group-3" label-for="input-3">
        <b-form-select
          label="Filter:"
          class="form-control"
          id="input-3"
          v-model="form.food"
          :options="foods"
          required
        ></b-form-select>
      </b-form-group>
    </b-row>
    <b-row>
      <b-col cols="9">
        <b-row>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
        </b-row>
        <b-row>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
        </b-row>
        <b-row>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
            </b-card>
          </b-col>
          <b-col>
            <b-card
              title="Card Title"
              img-src="https://via.placeholder.com/350x150"
              img-alt="Image"
              img-top
              tag="article"
              style="max-width: 20rem"
              class="mb-2"
            >
              <b-card-text>
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </b-card-text>

              <b-button  variant="primary"><router-link class="text-light" :to="{name: 'postDetails', params: {id:2}}">Read More...</router-link></b-button>
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
  data: function () {
    return {
      form: {
        food: null
      },
      foods: [
        { text: 'Filter Post', value: null },
        'Category-1',
        'Category-2',
        'Category-3',
        'Category-4'
      ],
      show: true
    }
  },
  components: {
    RightSidebar,
    BRow,
    BCol,
    BFormGroup,
    BFormSelect
  }
}
</script>
