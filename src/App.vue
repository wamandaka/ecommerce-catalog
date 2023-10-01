<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'
import axios from "axios";
import { ref } from "vue";

const judul = ref("Ecommerce Catalog");
const info = ref([]);

axios.get("https://fakestoreapi.com/products").then((response) => {
  info.value = response.data;
  // console.log(response.data);
});
</script>

<template>
  <img src="./img/men.png" alt="women" />
  <table>
    <thead>
      <th>No</th>
      <th>Title</th>
      <th>Price</th>
      <th>Category</th>
      <th>Description</th>
    </thead>
    <tbody>
      <!-- <tr v-for="item in info" :key="item.id">
        <td>{{ item.id }}</td>
        <td>{{ item.title }}</td>
        <td>{{ item.price }}</td>
        <td>{{ item.category }}</td>
        <td>{{ item.description }}</td>
      </tr> -->
      <td>{{ info[0].id }}</td>
      <td>{{ info[0].title }}</td>
      <td>{{ info[0].price }}</td>
      <td>{{ info[0].category }}</td>
      <td>{{ info[0].description }}</td>
    </tbody>
  </table>
</template>

<style scoped>
img {
  width: 50%;
}
td {
  padding: 1rem;
}
/* header {
  line-height: 1.5;
} */

/* .logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
