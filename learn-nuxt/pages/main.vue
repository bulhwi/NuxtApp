<template>
  <div>
    <p>
      메인
    </p>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'Main',
  async created() {
    const response = await axios.get("http://localhost:3000/products");
    console.log(response);
  }
};
</script>

<style scoped>

</style>
