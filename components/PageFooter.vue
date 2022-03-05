<template>
  <div v-show="visible" class="footer">
  </div>
</template>

<script>
export default {
  data () {
    return {
      notShown: ['index','test'],
    }
  },
  computed: {
    visible () {
      if (this.notShown.includes(this.$route.name)) {
        return false;
      }
      return true;
    }
  }
}
</script>

<style>
.footer {
  margin: 0 auto;
  position: relative;
  text-align: center;
  width: 90%; 
  left: 0;
  bottom: 0;
  padding-top: 10vh;
}
</style>