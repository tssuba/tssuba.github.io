<template>
  <article>
    <h1>{{ article.title }}</h1>
    <p class="article__description">{{ article.description }}</p>
    <!-- <img :src="article.img" :alt="article.alt"/> -->
    <br/>
    <div>
      <p class="article__updatedAt">{{ formatDate(article.updatedAt) }}</p>
      <ReadingTime :content="article"/>
    </div>
    <nuxt-content :document="article" />

    <PrevNext :prev="prev" :next="next" />
  </article>
</template>

<script>
  export default {
    async asyncData({ $content, params }) {
      const article = await $content('articles', params.slug).fetch()
      
      const [prev, next] = await $content('articles')
        .only(['title', 'slug'])
        .sortBy('createdAt', 'asc')
        .surround(params.slug)
        .fetch()
      
      return {
        article,
        prev,
        next
      }
    },
    methods: {
      formatDate(date) {
        const options = { year: 'numeric', month: 'long', day: 'numeric' }
        return new Date(date).toLocaleDateString('en', options)
      }
    }
  }
</script>

<style>
article {
  color: white;
}

.nuxt-content {
  margin-top: 7vh;
  margin-bottom: 10vh;
}

.nuxt-content p {
  font-size: .85em !important;
  line-height: 2em !important;
  margin-bottom: 3vh;
  font: inherit;
}

.nuxt-content a {
  text-decoration: none;
  color: #00cc92;
  border-bottom: .5px solid;
}

.article__description {
  font-style: italic;
}

.article__description, .article__updatedAt {
  font-size: .85em;
}
</style>