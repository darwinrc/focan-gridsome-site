<template>
  <div class="layout">

    <nav class="flex items-center justify-between flex-wrap bg-teal-500 p-6 md:hidden">
      <div class="flex items-center flex-shrink-0 text-white mr-5">
        <img class="logo-responsive" alt="FOCAN Logo" src="../assets/logo-home.png" />
  </div>
  <div class="block lg:hidden">
    <button class="flex items-center px-3 py-2 border rounded text-teal-200 border-teal-400 hover:text-white hover:border-white" @click="toggleMenu">
      <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
    </button>
  </div>
  <div v-if="isMenuVisible" class="flex w-full justify-between">
    <div class="text-sm">
      <g-link class="block mt-4 text-teal-200 hover:text-white mr-4 text-4xl" to="/news/">NOTICIAS</g-link>
      <g-link class=" block mt-4 text-teal-200 hover:text-white mr-4 text-4xl" to="/shop/">TIENDA</g-link>
      <g-link class="block mt-4 text-teal-200 hover:text-white text-4xl" to="/stories/">HISTORIAS</g-link>
    </div>
    <div>
    <div>
      <a href="#" class="inline-block text-4xl px-5 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0">Donaciones</a>
    </div>
    <div>
      <a href="#" class="inline-block text-4xl px-8 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0">Urgencias</a>
    </div>
    </div>
  </div>
</nav>
<!--   
    <header class="header">
      <strong>
        <g-link to="/">{{ $static.metadata.siteName }}</g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about/">About</g-link>
      </nav>
    </header>
    -->
    <slot/>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
   data:  () => {
    return {
      isMenuVisible: false  
    }
  },
  methods:{
    toggleMenu () {
      this.isMenuVisible = !this.isMenuVisible
    }
  }
}
</script>

<style lang="scss">
*{
  font-size: 10px;
}
body {
  font-family: -apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
}

a {
  text-decoration: none;
  color: #00B8D4;

  &:hover {
    color: #B2EBF2;
  }
  
  &:active {
    color: #B2EBF2;
  }
}

.logo-responsive {
  width:100px;
  height: auto;
}
</style>
