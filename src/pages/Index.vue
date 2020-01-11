<template>
  <Layout>

    <main>
      <section>
        <div class="stories">
          <StoryCard v-for="story in stories" 
              :name="story.name" 
              :image="story.image" 
              :key="story.name"/>
        </div>
      </section>
      <section>
        <g-image class="cat-background" alt="FOCAN Logo" src="~/assets/cat.png" />
         <div class="logo">
          <g-image class="logo__img" alt="FOCAN Logo" src="~/assets/logo-home.png" />
        </div>
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
          </nav>
        </header>
        <nav class="nav-tabs">
          <div class="nav-tabs__container">
            <div class="nav-tabs__tab">
              <span class="nav-tabs__icon">$</span>
              <span class="nav-tabs__text">DONACIONES</span>
            </div>
          </div>
          <div class="nav-tabs__container">
            <div class="nav-tabs__tab">
              <span class="nav-tabs__icon">+</span>
              <span class="nav-tabs__text">URGENCIAS</span>
            </div>
          </div>
        </nav>
      </section>
    </main>
    

    <modal name="story-modal">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Rem asperiores molestiae debitis reprehenderit, minima enim possimus repudiandae facere dolor saepe in vel nulla nihil eos odio quam mollitia adipisci dicta voluptatum qui blanditiis! Nemo, repellendus. Numquam ducimus in iste vitae vel accusantium tenetur culpa aut quaerat, quae nobis provident debitis?
    </modal>

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
import StoryCard from '~/components/StoryCard.vue';

export default {
  metaInfo: {
    title: 'FOCAN - Fondo para el Cuidado Animal'
  },
  data () {
    return {
      stories: [
        {
          name: 'Caspar',
          image: 'dog1.jpg'
        },
        {
          name: 'Mayo',
          image: 'cat1.jpg'
        },
        {
          name: 'Petulia',
          image: 'dog2.jpg'
        },
        {
          name: 'Truco',
          image: 'cat2.jpg'
        },{
          name: 'Luna',
          image: 'dog3.jpg'
        },
        {
          name: 'Samba',
          image: 'cat3.jpg'
        },
        {
          name: 'Romeo',
          image: 'dog4.jpg'
        },
        {
          name: 'Dora',
          image: 'cat4.jpg'
        },
        {
          name: 'Jose',
          image: 'catdog.jpg'
        },
      ]
    }
  },
  components: {
    StoryCard
  },

  methods:{
    show () {
      this.$modal.show('hello-world');
    },
    hide () {
      this.$modal.hide('hello-world');
    }
  }
}
</script>

<style lang="scss" scoped>
  main {
    display: flex;
    width: 100%;

     @media (max-width: $breakpoint-mobile-portrait) {
      flex-direction: column-reverse;
    }
  }

  section {
    display: flex;
    flex-direction: column;
    width: 50%;
    height: 100vh;
    border-right: 1px solid lightgray;

    @media (max-width: $breakpoint-mobile-portrait) {
      width: 100%;
      height: 100%;
    }

    &:last-child {
      position: relative;
    }
  }

  .cat-background {
    width: 100%;
    height: 100%;
    position: absolute;
    z-index: -1;
    opacity: .7;

    @media (max-width: $breakpoint-mobile-portrait) {
      width: 0;
      height: 0;
    }
  }

  .logo {
    width: 20rem;
    margin: 1rem auto;

    @media (max-width: $breakpoint-mobile-portrait) {
      display: none;
    }    

    &__img {
      border-radius: 63%;
      height: 20rem;
      width: 20rem;

      @media (max-width: $breakpoint-mobile-portrait) {
        width: 10rem;
        height: 10rem;
      }
    }
  }

  .stories {
    display: grid;
    grid-template-columns: repeat(3, 21rem);
    grid-template-rows: repeat(3, 30rem);
    grid-gap: 1rem;
    justify-content: center;
    align-items: center;
    margin: 1rem 0 1rem;

    @media (max-width: $breakpoint-mobile-portrait) {
      grid-template-columns: repeat(1, 1fr);
      grid-template-rows: repeat(9, 1fr);
    }
  }

  .nav {
    margin: 7rem;
    display: flex;
    flex-direction: column;
    align-items: center;

    @media (max-width: $breakpoint-mobile-portrait) {
      display: none;
    }

    &__link {
      font-size: 13rem;
      font-weight: 600;

      &--danger {
        align-self: center;
        color: white;
        background: red;
        line-height: 10rem;
        border-radius: 10rem;
        padding: 2rem;
        position: absolute;
        top: -43px;
        right: 3px;
        height: 100px;
        font-size: 3rem;
      }
    }
  }

  .nav-tabs {
    @media (max-width: $breakpoint-mobile-portrait) {
      display: none;
    }  
    &__container {
      overflow: hidden;
      position: absolute;
      right: 0;
      top: 0;
      
      &:last-child {
        top: 5rem;
      }
    }
    
    &__tab {
      cursor: pointer;  
      border-top: 1px solid red;
      border-bottom: 1px solid red;
      border-radius: 5rem 0 0 5rem;
      color: white;
      background: red;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: 1rem auto;
      transition: all .6s ease-in-out;
      margin-right: -21rem;

      &:hover {
        margin-right: 0;
      }
    }

    &__icon {
      font-size: 3rem;
      font-weight: 600;
      border-right: 1px solid white;
      padding: 0 1rem;
      width: 5rem;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    &__text {
      font-size: 3rem;
      font-weight: 600;
      background: white;
      color: gray;
      width: 21rem;
      text-align: center;
    }
  }
</style>
