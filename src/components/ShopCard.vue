<template>
<figure class="shop-card">
    <g-image class="shop-card__img" 
            :alt="description" 
            :src="require('!!assets-loader!~/assets/shop/' + image)"/>
    <figcaption class="shop-card__footer">
        <p>{{description}}</p> 
    </figcaption>
</figure>
</template>

<script>
export default {
  props: [
    'image',
    'description',
  ],
}
</script>

<style lang="scss" scoped>
p {
  font-size: 2rem;
  margin: 0;
  margin-top: -0.4rem;
  padding: 0 1.5rem;
}

.shop-card {
  margin: 1rem 0;
  transition: all .6s ease-in-out;

  @media (max-width: $breakpoint-mobile-portrait) {
      font-size: 1rem;
      transition: none;
  }

  &:hover {
      transform: scale(1.5);
      @media (max-width: $breakpoint-mobile-portrait) {
        transform: none;
      }
  }

  &__img {
    width: 100%;
  }

  &__footer {
     background: #e0f7fa78;
  }
}
</style>
