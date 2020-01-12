<template>
  <Layout>
    <h1>TIENDA SOLIDARIA</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
 <section class="shop__gallery">
      <ShopCard v-for="item in items" 
                :description="item.description" 
                :image="item.image" 
                :key="item.image"/>
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
      items: [
        {
          image: 'shop1.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop2.jpg',
          description: 'Donec sed odio operae, eu vulputate felis rhoncus.'
        },
        {
          image: 'shop3.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop4.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop5.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop6.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop7.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop8.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop9.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop10.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop11.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
        {
          image: 'shop12.jpg',
          description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
        },
      ]
    }
  },
   components: {
    ShopCard
  },
}
</script>

<style lang="scss" scoped>
  h1 {
    font-size: 7rem;
    font-weight: 600;
    text-align: center;
    color: #00B8D4;

    @media (max-width: $breakpoint-mobile-portrait) {
      font-size: 3rem;
      margin: 1rem;
    }
  }

  p {
    font-size: 2rem;
    
    @media (max-width: $breakpoint-mobile-portrait) {
      font-size: 1rem;
      margin: 1rem;
    }
  }

  .shop{
    &__gallery {
      columns: 3 20rem;
      column-gap: 2rem;
      -webkit-column-break-inside: avoid;
      page-break-inside: avoid;
      break-inside: avoid;
    }
  }
</style>
