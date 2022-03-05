<template>
  <nav v-if="visible" class="navbar">
    <router-link v-for="(l, idx) in links" :key="idx" :to="l.link" class="navlinks" exact>{{ l.title }}</router-link>
  </nav>
</template>

<script>
export default {
  data () {
    return {
      disableView: ['index'], // disable for certain routes 
      links: [
        {
          title: 'home',
          link: '/'
        },
        /*{
          title: 'work',
          link: '/work'
        },*/
          {
            title: 'resume',
            link: '/resume'
          },
        {
          title: 'contact',
          link: '/contact'
        }
      ]
    }
  },
  computed: {
    visible () {
      if (this.disableView.includes(this.$route.name)) {
        return false;
      } else {
        return true;
      }
    },
  },
}
</script>

<style>
.navbar {
  margin-top: 25vh;
  margin-bottom: 10vh;
  text-align: center;
}

.navbar a.nuxt-link-exact-active {
  color: #00c58e;
  border-bottom: solid .5px;
}

.navlinks {
  margin-left: 1vw;
  margin-right: 1vw;
  font-size: .75em;
  text-decoration: none;
  color: white;
  text-transform: uppercase;
}

.navlinks:hover {
  color: #00c58e;
  border-bottom: solid .5px;
}
</style>
