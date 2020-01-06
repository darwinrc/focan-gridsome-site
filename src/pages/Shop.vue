<template>
  <Layout>
    <h1>Tienda Solidaria</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Error doloremque omnis animi, eligendi magni a voluptatum, vitae, consequuntur rerum illum odit fugit assumenda rem dolores inventore iste reprehenderit maxime! Iusto.</p>
 <section class="Shop__gallery">
  <g-image class="Shop__img"  
            src="~/assets/shop/shop1.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop2.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop3.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop4.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop5.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop6.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop7.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop8.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop9.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop10.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop11.jpg"/>
  <g-image class="Shop__img"  
            src="~/assets/shop/shop12.jpg"/>
 </section>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Tienda Solidaria'
  }
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
