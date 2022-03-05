<template>
  <div v-show="visible" class="page__title_container">
    <h2 class='page__title'>
      <NuxtLink :to="`/${sectionRoute}`">{{ title }}</NuxtLink>
    </h2>
  </div>
</template>

<script>
export default {
  data () {
    return {
      notShown: ['index'],
    }
  },
  computed: {
    visible () {
      if (this.notShown.includes(this.$route.name)) {
        return false
      } else {
        return true
      }
    },
    title () {
      let currRoute = this.$route.name;
      
      if (currRoute == 'about') {
        currRoute = currRoute + ' me';
      } else if (this.$route.name == 'works-slug') {
        currRoute = 'works';
      } 

      return currRoute
    },
    sectionRoute () {
      return this.$route.name.split('-')[0];
    },
  }
}
</script>

<style>
.page__title {
  text-align: center;
  margin-top: 25vh;
  margin-bottom: 10vh;
  text-decoration: none;
}

.page__title a {
  color: white;
  text-decoration: none;
  text-transform: uppercase;
  letter-spacing: .5em;
}

.page__title a:hover {
  color: #00cc92;
}

@media screen and (max-width: 426px) {
  .page__title {
    display: none;
  }
}
</style>