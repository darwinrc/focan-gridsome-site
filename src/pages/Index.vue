<template>
  <Layout>

    <main>
      <section>
        <div class="logo">
          <g-image class="logo__img" alt="FOCAN Logo" src="~/assets/logo-home.png" />
        </div>
        <div class="stories">
          <div class="stories__card">
            <div class="stories__card-header">
              Caspar
            </div>
            <g-image class="stories__img" alt="Example image" src="~/assets/dog1.jpg" />
          </div>
          <div class="stories__card">
            <div class="stories__card-header">
              Samba
            </div>
            <g-image class="stories__img" alt="Example image" src="~/assets/cat1.jpg"/>
          </div>
           <div class="stories__card">
            <div class="stories__card-header">
              Petulia
            </div>
            <g-image class="stories__img" alt="Example image" src="~/assets/dog2.jpg"/>
          </div>
          <div class="stories__card">
            <div class="stories__card-header">
              Lucas
            </div>
            <g-image class="stories__img" alt="Example image" src="~/assets/cat2.jpg"/>
          </div>
        </div>
      </section>
      <section>

        <header class="header">
        <!--
          <strong>
            <g-link to="/">{{ $static.metadata.siteName }}</g-link>
          </strong>
          -->
          <nav class="nav">
            <g-link class="nav__link nav__link--danger" to="/urgent/">Urgentes</g-link>
            <g-link class="nav__link" to="/news/">Noticias</g-link>
            <g-link class="nav__link" to="/shop/">Tienda Solidaria</g-link>
            <g-link class="nav__link" to="/stories/">Historia</g-link>
            <g-link class="nav__link" to="/about/">Acerca de FOCAN</g-link>
          </nav>
        </header>
      </section>
    </main>
    

    

  </Layout>
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
  metaInfo: {
    title: 'FOCAN - FOndo para el Cuidado Animal'
  }
}
</script>

<style lang="scss">
  main {
    display: flex;
    width: 100%;
  }

  section {
    width: 50%;
    height: 100vh;
    border-right: 1px solid gray;
  }

  .logo {
    width: 50rem;
    margin: 5rem auto;

    &__img {
      width: 100%;
    }
  }

  .stories {
    display: grid;
    grid-template-columns: repeat(3, 21rem);
    grid-template-rows: repeat(3, 20rem);
    grid-gap: 1rem;
    justify-content: center;

    &__card {
      border: .5rem solid gray;

      &:nth-child(1) {
        grid-row-start: 1;
        grid-column-start: 2;
      }
      
      &:nth-child(2) {
        grid-row-start: 2;
        grid-column-start: 1;
      }

      &:nth-child(3) {
        grid-row-start: 2;
        grid-column-start: 3;
      }

      &:nth-child(4) {
        grid-row-start: 3;
        grid-column-start: 2;
      }
    }

    &__card-header {
      background-color: #E0F7FA;
      height: 5rem;
      font-size: 3rem;
      width: 50%;
      border: 1px solid gray;
      margin-bottom: .5rem;
    }

    &__img {
      width: 20rem;
    }
  }

  .nav {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;

    &__link {
      font-size: 5rem;
      line-height: 15rem;

      &--danger {
        color: red;

        &:hover, &:active {
          color: pink;
        }
      }
    }
  }
</style>
