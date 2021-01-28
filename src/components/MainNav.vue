<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light" id="MainNav">
    <a class="navbar-brand" href="#">Navbar</a>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
      v-on:click="toggleNav()"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div
      class="navbar-collapse collapse"
      id="navbarSupportedContent"
      v-bind:class="{ show: !isOpened }"
    >
      <ul class="navbar-nav ml-auto">
        <!-- <li class="nav-item active">
          <router-link to="/" class="nav-link">
            Home
            <span class="sr-only">(current)</span>
          </router-link>
        </li> -->
        <li class="nav-item">
          <router-link class="nav-link" to="/ProductPage">Products</router-link>
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/add_product"
            >Add Product</router-link
          >
        </li>
        <li class="nav-item">
          <router-link class="nav-link" to="/CartPage"
            >Cart <span>{{ cartItems.length }}</span></router-link
          >
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "MainNav",

  data() {
    return {
      isOpened: false,
    };
  },

  methods: {
    toggleNav() {
      this.isOpened = !this.isOpened;
    },
  },

  computed: {
    cartItems() {
      return this.$store.state.cartItems;
    },
  },
};
</script>

<style scoped>
.router-link-exact-active {
  color: red !important;
}
</style>
