<template>
  <div class="content__img">
    <img :src="imgSrc()" :alt="alt" />
  </div>
</template>

<script>
export default {
  props: {
    src: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      required: true
    }
  },
  methods: {
    imgSrc() {
      try {
        return require(`~/static/images/${this.$route.params.slug}/${this.src}`);
      } catch (error) {
        return null
      }
    }
  }
}
</script>

<style>
.content__img {
  text-align: center;
}
.content__img * {
  width: 100%;
  max-width: 850px;
  height: auto;
  margin: 15px 0 15px 0;
}
</style>