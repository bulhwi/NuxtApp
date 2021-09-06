<template>
  <div>
    <header>
      <h1>{{ $route.name }} 페이지</h1>
      <nuxt-link to='/'>홈페이지</nuxt-link>
      <nuxt-link to='/product'>상품 홈페이지</nuxt-link>
    </header>
    <Nuxt />
  </div>
</template>

<script>
export default {
  name: 'Default',
};
</script>

<style scoped>

</style>
