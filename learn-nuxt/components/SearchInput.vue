<template>
  <div>
    <input type='text'
           :value='searchKeyWord'
           @input='$emit("input", $event.target.value)'
    />
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    searchKeyWord: {
      type: String,
      default: () => ''
    }
  }
};
</script>

<style scoped>

</style>
