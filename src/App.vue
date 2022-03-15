<template>
  <div id="app">
    <header class="home">
      <div class="flex justify-between px-5 py-5">
        <div class="font-caveat text-5xl black-sense font-black">Logo</div>
        <SocialComponent />
      </div>
      <div class="font-caveat px-24 py-32 text-7xl black-sense font-bold">
        El secreto 
        <p class="absolute z-20">de tu cocina</p>
        <img class="brush-img" src="./assets/brush.png" alt="" />
      </div>
    </header>
    <div class="our-articles">
      <div class="subtitle font-caveat text-center black-sense text-7xl font-bold py-8">
        Nuestros artículos
      </div>
      <section class="flex justify-around aligns-center w-10/12 m-auto">
        <div class="bg-white shadow-xl py-5 h-64 rounded-sm">
          <MenuComponent />
        </div>
        <div class="product-card mx-4">
          <ProductsCard />
        </div>
      </section>
    </div>
    <div class="contact-us">
      <div class="subtitle black-sense font-caveat text-center text-7xl font-bold py-24">
        Contáctanos
      </div>
      <ContactUS />
    </div>
  </div>
</template>

<script>
export default {
  components: { 
    SocialComponent: () => import('./components/social'),
    MenuComponent: () => import('./components/menu'),
    ProductsCard: () => import('./components/product'),
    ContactUS: () => import('./components/contactus')
  },
  data() {
    return {

    }
  }
}
</script>


<style src="./assets/tailwind.css">