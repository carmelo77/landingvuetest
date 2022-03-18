<template>
  <div id="app">
    <header class="home">
      <div class="flex justify-between px-5 py-5">
        <div class="font-caveat text-5xl black-sense font-black animate__animated animate__fadeInLeft">Logo</div>
        <SocialComponent />
      </div>
      <div class="font-caveat px-24 py-32 text-7xl black-sense font-bold">
        El secreto 
        <p class="absolute z-20 animate__animated animate__fadeInLeft">de tu cocina</p>
        <img class="brush-img" src="./assets/brush.png" alt="" />
      </div>
    </header>
    <div class="our-articles">
      <div class="subtitle font-caveat text-center black-sense text-7xl font-bold py-8 animate__animated animate__fadeInDown">
        Nuestros artículos
      </div>
      <section class="flex justify-around aligns-center w-10/12 m-auto">
        <div>
          <div class="bg-white shadow-xl py-5 h-64 rounded-sm">
            <MenuComponent />
          </div>
          <div class="w-full flex pb-5 justify-center">
          <input
            type="text"
            name="search"
            v-model="search"
            @keyup.enter="getProducts()"
            placeholder="Search category...."
            class="px-2 py-2 my-2 rounded border border-gray-300 focus:outline-none focus:ring-2 focus:ring-gray-200"
          />
        </div>
        </div>
        <div class="product-card mx-4">
          <pulse-loader 
            :loading="isLoading" 
            color="black" 
          />
          <ProductsCard 
            :items="products"
          />
        </div>
      </section>
    </div>
    <div class="contact-us">
      <div class="subtitle black-sense font-caveat text-center text-7xl font-bold py-24 animate__animated animate__fadeInDown">
        Contáctanos
      </div>
      <ContactUS />
    </div>
  </div>
</template>

<script>
import PulseLoader from 'vue-spinner/src/PulseLoader.vue'
import { BASE_URL } from './api/api';

export default {
  components: { 
    SocialComponent: () => import('./components/social'),
    MenuComponent: () => import('./components/menu'),
    ProductsCard: () => import('./components/product'),
    ContactUS: () => import('./components/contactus'),

    PulseLoader: PulseLoader,
  },
  data() {
    return {
      search: '',
      isLoading: false,
      products: []
    }
  },

  mounted() {
		this.getProducts();
	},

  methods: {
    getProducts() {
			this.isLoading = true;
      this.products = [];

			fetch(`${BASE_URL}/articles?filter=${this.search}`).then(res => {
				return res.json();
			})
			.then(response => {
				this.products = response;
				this.isLoading = false;
			})
			.catch(err => {
				console.log(err)
				this.isLoading = false;
			})
		}
  }
}
</script>


<style src="./assets/tailwind.css">