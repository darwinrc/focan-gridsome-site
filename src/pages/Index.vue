<template>
  <Layout>

    <main>
      <section>
        <!-- <div class="logo">
          <g-image class="logo__img" alt="FOCAN Logo" src="~/assets/logo-home.png" />
        </div> -->
        <div class="stories">
          <StoryCard v-for="story in stories" 
              :name="story.name" 
              :image="story.image" 
              :key="story.name"/>
        </div>
        <!-- <g-link class="nav__link nav__link--danger urgent" to="/urgent/">URGENTES</g-link> -->
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
            <g-link class="nav__link nav__link--danger" to="/urgent/">DONAR</g-link>
          </nav>
        </header>
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
  }

  .logo {
    width: 20rem;
    margin: 1rem auto;

    &__img {
      width: 200px;
      border-radius: 63%;
      height: 200px;
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
  }

  .nav {
    margin: 7rem;
    display: flex;
    flex-direction: column;
    align-items: center;

    &__link {
      font-size: 13rem;

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

  .urgent {
    font-size: 2rem;
  }
</style>
