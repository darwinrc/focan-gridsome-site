<template>
  <div class="layout">
    <nav class="flex items-center justify-between flex-wrap bg-teal-500 p-6 md:hidden">
      <div class="flex items-center flex-shrink-0 text-white mr-5">
        <img class="logo-responsive" alt="FOCAN Logo" src="../assets/logo-home.png" />
      </div>
      <div class="block lg:hidden">
        <button
          class="flex items-center px-3 py-2 border rounded"
          @click="toggleMenu"
        >
          <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div v-if="isMenuVisible" class="flex w-full justify-between">
        <div class="text-sm">
          <g-link
            class="block mt-4 text-teal-200 hover:text-white mr-4 text-4xl"
            to="/news/"
          >NOTICIAS</g-link>
          <g-link class="block mt-4 text-teal-200 hover:text-white mr-4 text-4xl" to="/shop/">TIENDA</g-link>
          <g-link
            class="block mt-4 text-teal-200 hover:text-white text-4xl"
            to="/stories/"
          >HISTORIAS</g-link>
        </div>
        <nav class="navPills">
          <div class="navPills__container">
            <div class="navPills__tab">
              <span class="navPills__icon"></span>
              <div class="navPills__text">
                <span class="navPills__text--white">DONAC</span>
                <span class="navPills__text--red">IONES</span>
              </div>
            </div>
          </div>
          <div class="navPills__container">
            <div class="navPills__tab">
              <span class="navPills__icon"></span>
              <div class="navPills__text">
                <span class="navPills__text--white">URGE</span>
                <span class="navPills__text--red">NCIAS</span>
              </div>
            </div>
          </div>
        </nav>
      </div>
    </nav>
    <slot />
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
  data: () => {
    return {
      isMenuVisible: false
    };
  },
  methods: {
    toggleMenu() {
      this.isMenuVisible = !this.isMenuVisible;
    }
  }
};
</script>

<style lang="scss">
* {
  font-size: 10px;
}
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
      "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}
.logo-responsive {
  width: 100px;
  height: auto;
}

.navPills {
  margin-top: 2rem;
  width: 16rem;
  margin-right: 2rem;

  &__tab {
    position: relative;
    border: 1px solid red;
    border-radius: 5rem;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 1rem auto;
  }

  &__icon {
    background-color: red;
    border-radius: 5rem 0 0 5rem;
    position: absolute;
    top: 0;
    left: 0;
    width: 50%;
    height: 100%;
    z-index: -1;
  }

  &__text {
    color: -webkit-linear-gradient(white, red);

    text-align: center;
    span {
      font-size: 2.25rem;
      font-weight: 400;
    }
    &--white {
      color: white;
    }

    &--red {
      color: red;
    }
  }
}
</style>
