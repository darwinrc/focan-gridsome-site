<template>
  <div class="layout">
    <nav class="nav">
      <div class="nav-logo">
        <img class="logo-responsive" alt="FOCAN Logo" src="../assets/logo-home.png" />
      </div>
      <div class="menu-icon">
        <button
          class="menu-icon__button"
          @click="toggleMenu"
        >
          <svg class="menu-icon__svg" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg">
            <title>Menu</title>
            <path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z" />
          </svg>
        </button>
      </div>
      <div v-if="isMenuVisible" class="menu-list">
        <div class="menu-list__link-wrap">
          <g-link class=" menu-list__link" to="/news/">NOTICIAS</g-link>
          <g-link class="menu-list__link" to="/shop/">TIENDA</g-link>
          <g-link class="menu-list__link" to="/stories/">HISTORIAS</g-link>
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

.nav {
  display: none;
  
  @media (max-width: $breakpoint-mobile-portrait) {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    padding: 1.5rem; 
  }
}

.nav-logo {
  display: flex;
  align-items: center;
}

.menu-icon {
  display: block;

  &__button {
    padding: 0.5rem 0.75rem;
    align-items: center;
    display: flex;
    border-width: 1px;
    border-radius: 0.25rem;
    background: none;
    border-style: groove;
  }

  &__svg {
    height: 0.75rem;
    width: 0.75rem;
  }
}

.menu-list {
  display: flex;
  justify-content: space-between;
  width: 100%;

  &__link-wrap {
    font-size: 0.875rem;
  }

  &__link {
    display: block;
    font-size: 2.25rem;
    margin-right: 1rem;
    margin-top: 1rem;
  }
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
