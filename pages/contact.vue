<template>
  <div class="contact">
    <div v-for="(l, idx) in contacts" :key="idx" class="contact__link_container">
      <a class="contact__link" :href="l.link" target="_blank">{{ l.title }}</a>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      contacts: [
          {
            title: 'Email',
            link: 'mailto:hellotanmay@pm.me'
          },
          /*{
            title: 'Linkedin',
            link: 'http://linkedin.com/in/tanmay-suba'
          },*/
          /*{ 
            title: 'Github',
            link: 'http://github.com/tssuba'
          }*/
        ],
    }
  }
}
</script>

<style>
.contact {
  margin-top: 20vh;
  display: flex;
  flex-direction: column;;
  text-align: center;
}

.contact__link_container {
  margin-bottom: 2vh;
}

.contact__link {
  font-size: .75em;
  text-decoration: none;
  color: white;
}
.contact__link:hover {
  color: #00c58e;
  border-bottom: .5px solid;
}

</style>
