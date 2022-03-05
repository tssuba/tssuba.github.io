<template>
  <div class="index__container">
    <div class="header__banner">
      <div class="header__item">
        <span class="header__name">{{ firstName}} {{ lastName }}</span>
      </div>
      <a class="header__links" v-for="(c, idx) in contacts" :key="idx" :href="c.link" target="_blank">{{ c.title }}</a>
    </div>
      <div class="header__navs_container">
        <NuxtLink class="header__navs" v-for="(n, idx) in navs" :key="idx" :to="n.destination">{{ n.title }}</NuxtLink>
      </div>
  </div>
</template>

<script>
export default {
  data () {
    return {  
      firstName: 'Tanmay',
      lastName: 'Suba',
      contacts: [
        {
          title: 'Email',
          link: 'mailto:hellotanmay@pm.me'
        },
        /*{
          title: 'Linkedin',
          link: 'http://linkedin.com/in/tanmay-suba'
        },*/
        {
          title: 'Github',
          link: 'http://github.com/tssuba'
        }
      ],
      navs: [
        /*{
          title: 'work',
          destination: '/work'
        },*/
        {
          title: 'resume',
          destination: '/resume'
        }
      ]
    }
  },
  computed: {
    splitCode () {
      return this.code.split('');
    },
    splitFirstName () {
      return this.firstName.split('');
    },
    splitLastName () {
      return this.lastName.split('');
    }
  }
}
</script>

<style>
.index__container * {
  color: white;
}

.index__container a:hover{
  color: #00cc92;
  border-bottom: solid .5px #00cc92;
}

.header__banner {
  margin-top: 25vh;
}

.header__name {
  text-transform: uppercase;
  font-weight: bold;
}

.header__links {
  text-decoration: none;
  font-size: .75em;
  line-height: 2em;
  margin-right: 1.5vw;
}

.header__navs_container {
  text-align: center;
  margin: auto;
  margin-top: 25vh;
}

.header__navs {
  text-decoration: none;
  /* float: right; */
  text-transform: uppercase;
  font-size: .8em;
  margin-left: 2vw;
  border-bottom: .5px solid;
}
</style>
