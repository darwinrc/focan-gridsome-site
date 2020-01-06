<template>
<figure class="ShopCard">
  <div class="ShopCard__header">
    <g-image class="ShopCard__img" :alt="description" 
            :src="require('!!assets-loader!~/assets/shop/' + image)"/>
  </div>
   <div class="ShopCard__overlay">
      <figcaption class="ShopCard__footer">
          <p>{{description}}</p> 
      </figcaption>
  </div>
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
  padding: 0 1.5rem;
}
.ShopCard {
  position: relative;
  margin: 1rem;

  &__header {
    position: relative;
    padding-bottom: 100%;
    overflow: hidden;
  }

  &__img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;  
  }

  &__overlay {
    background: black;
    opacity: 0;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    &:hover { 
      opacity: .7;
    } 

    figcaption {
      position:absolute;
      top: auto;
      bottom:0;
      background:hsla(0,0%,100%,.85);
      color:#3c4a50;
      width: 100%;
    }
  }
}
</style>
