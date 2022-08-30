<template>
    <div class="page-product">
        <div class="columns is-multiline">
            <div class="column is-9">
                <figure class="image mb-6">
                    <img v-bind:src="product.get_image" alt="image">
                </figure>
                <h1 class="title">{{product.name}}</h1>

                <p>{{product.description}}</p>
            </div>

            <div class="column is-3">
                <h2 class="subtitle">Information</h2>
                <p><strong>Price:</strong>${{product.price}}</p>
                <div class="control">
                    <input class="input" type="number" v-model="quantity" min=1 placeholder="Quantity">
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'product',
  data() {
    return {
        product: {},
        quantity: 1
    };
  },
  components: {
  },
  mounted() {
    this.getProduct();
  },
  methods: {
    getProduct(){
        const category_slug = this.$route.params.category_slug;
        const product_slug = this.$route.params.product_slug;
    }
  },
}

</script>