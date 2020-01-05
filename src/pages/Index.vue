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
        <g-link class="nav__link nav__link--danger urgent" to="/urgent/">URGENTES</g-link>
      </section>
      <section>

        <header class="header">
        <!--
          <strong>
            <g-link to="/">{{ $static.metadata.siteName }}</g-link>
          </strong>
          -->
          <nav class="nav">
            <g-link class="nav__link" to="/news/">NOTICIAS</g-link>
            <g-link class="nav__link" to="/shop/">TIENDA</g-link>
            <g-link class="nav__link" to="/stories/">HISTORIA</g-link>
            <g-link class="nav__link nav__link--danger" to="/urgent/">DONAR</g-link>
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
    display: flex;
    flex-direction: column;
    width: 50%;
    height: 100vh;
    border-right: 1px solid lightgray;
  }

  .logo {
    width: 20rem;
    margin: 1rem;

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
    align-items: center;
    margin: 5rem 0 1rem;

    &__card {
      cursor: pointer;
      position: relative;

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
      background: #e0f7fa78;
      font-size: 3rem;
      width: 50%;
      position: absolute;
      margin-top: -3rem;
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
      font-size: 13rem;

      &--danger {
        color: white;
        background: red;
        line-height: 10rem;
        border-radius: 10rem;
        padding: 2rem;
        bottom: 1rem;
        position: absolute;
      }
    }
  }

  .urgent {
    align-self: center;
    font-size: 9rem;
  }
</style>
