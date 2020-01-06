<template>
<div class="StoryCard" @click="showStory">
    <div class="StoryCard__header">{{name}}</div>
    <g-image class="StoryCard__img" :alt="name" 
            :src="require('!!assets-loader!~/assets/' + image)"/>
</div>
</template>

<script>
export default {
  props: [
    'name',
    'image'
  ],
  methods:{
    showStory () {
      this.$modal.show('story-modal');
    },
    hideStory () {
      this.$modal.hide('story-modal');
    }
  }
}
</script>

<style lang="scss">
.StoryCard {
    cursor: pointer;
    position: relative;

    transition: all .6s ease-in-out;

    &:hover {
        transform: scale(1.7);
        z-index: 10;
    }

    &__header {
        background: #e0f7fa78;
        font-size: 3rem;
        position: absolute;
        margin-top: -3rem;
        padding: 0 1rem;
        z-index: 10;
    }

    &__img {
        width: 20rem;
        opacity: .6;
        transform: rotate(90deg);

        transition: all .6s ease-in-out;

        &:hover {
            opacity: 1;
        }
    }
}
</style>