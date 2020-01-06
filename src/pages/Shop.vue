<template>
  <Layout>
    <h1>Tienda Solidaria</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
 <section class="Shop__gallery">
    <ShopCard class="Shop__img"
              v-for="article in articles" 
              :name="article.name" 
              :image="article.image" 
              :key="article.name"/>
 </section>
  </Layout>
</template>

<script>
import ShopCard from '~/components/ShopCard.vue';

export default {
  metaInfo: {
    title: 'Tienda Solidaria'
  },
  data () {
    return {
      articles: [
        {
          name: 'Caspar',
          image: 'shop1.jpg'
        },
        {
          name: 'Mayo',
          image: 'shop2.jpg'
        },
        {
          name: 'Petulia',
          image: 'shop3.jpg'
        },
        {
          name: 'Truco',
          image: 'shop4.jpg'
        },{
          name: 'Luna',
          image: 'shop5.jpg'
        },
        {
          name: 'Samba',
          image: 'shop6.jpg'
        },
        {
          name: 'Romeo',
          image: 'shop7.jpg'
        },
        {
          name: 'Dora',
          image: 'shop8.jpg'
        },
        {
          name: 'Jose',
          image: 'shop9.jpg'
        },
      ]
    }
  },
   components: {
    ShopCard
  },
}
</script>

<style lang="scss">
  Layout {
    display: flex;
    flex-direction: column;
  }

  .Shop{
    &__gallery {
       display: grid;
      grid-template-columns: repeat(3, 21rem);
      grid-template-rows: repeat(4, 30rem);
      grid-gap: 1rem;
      justify-content: center;
      align-items: center;
      margin: 1rem 0 1rem;
      width: 100vw;
      height: 100vh; 
    }

    &__img {
      width: 20rem;
      height: 20rem;
    }
  }
</style>
