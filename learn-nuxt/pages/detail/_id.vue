<template>
  <div>
    <div class='container'>
      <div class='main-panel'>
        <img class='product-image'
             :src='product.imageUrl'
             :alt='product.name' />
      </div>
      <div class='side-panel'>
        <p class='name'>{{product.name}}</p>
        <p class='price'>{{product.price}}</p>
<!--        <button type='button' @click='addToCart'>Add to Cart</button>-->
      </div>
    </div>
  </div>
</template>

<script>

import { fetchProductById } from '~/api';

export default {
  async asyncData({ params, $http, error }) {
    try {
      const response = await fetchProductById(params.id);
      const product = response.data;
      return { product };
    } catch (e) {
      error({ statusCode: 503, message: 'API 요청이 실패했습니다. 다시 시도해 주세요.' });
    }
  },

  methods: {
    async addToCart() {
      // await createCartItem(this.product);

    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}
.product-image {
  width: 500px;
  height: 375px;
}
.side-panel {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 220px;
  text-align: center;
  padding: 0 1rem;
}
</style>
