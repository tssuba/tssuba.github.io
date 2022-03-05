<template>
  <div>
    <div v-if="displayTags">
      <ul class="selectedTags">
        <span class="tagTitle">Tags:</span>
        <span @click="popTags(t)" v-for="(t,idx) in selectedTag" :key="idx" class="tags">
          {{ t }}
          <span class="tagClose">X</span>
        </span>
        <span @click="clearAllTags" class="clearTags">Clear All</span>
      </ul>
    </div>
    <ul>
      <li v-for="article of articles" :key="article.slug" class="article__container">
        <NuxtLink :to="{ name: 'work-slug', params: { slug: article.slug } }" class="article__title">
          {{ article.title }}
        </NuxtLink>
        <p class="article__updatedAt">{{ formatDate(article.updatedAt) }}</p>
        <div v-if="article.tags">
          <span @click="pushTags(t)" v-for="(t, idx) in article.tags" :key="idx" class="tags">{{ t }}</span>
        </div>
        <NuxtLink :to="{ name: 'work-slug', params: { slug: article.slug } }" class="article__readmore">
          Read More
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        selectedTag: [],
        displayTags: false,
      }
    },
    async asyncData({ $content }) {
      const articles = await $content('articles')
        .only(['title', 'description', 'img', 'slug', 'author', 'updatedAt', 'tags'])
        .sortBy('createdAt', 'desc')
        .fetch()
      
      return {
        articles
      }
    },
    methods: {
      formatDate(date) {
        const options = { year: 'numeric', month: 'long', day: 'numeric' }
        return new Date(date).toLocaleDateString('en', options)
      },
      async searchByTags(c) {
        this.articles = await this.$content('articles')
          .where({ tags : { $contains: c }})
          .sortBy('createdAt', 'desc')
          .fetch()
      },
      pushTags (tag) {
        if (!this.selectedTag.includes(tag)) {
          this.selectedTag.push(tag);
          this.displayTags = true;
          this.searchByTags(this.selectedTag);
        }
      },
      async popTags (tag) {
        if (this.selectedTag.includes(tag)) {
          this.selectedTag = this.selectedTag.filter(ele => ele !== tag);
        }

        if (this.selectedTag.length === 0) {
          this.displayTags = false;
          await this.$nuxt.refresh();
        } else {
          await this.searchByTags(this.selectedTag); 
        }
      },
      async clearAllTags () {
        this.selectedTag = [];
        this.displayTags = false;
        await this.$nuxt.refresh();
      }
    }
  }
</script>

<style>
ul {
  padding-inline-end: 40px !important;
}

.article__container {
  padding-bottom: 5vh;
  margin-bottom: 7vh;
}

.article__container * {
  color: white;
  text-decoration: none;
}

.article__title {
  font-size: 1.25em;
}

.article__readmore {
  font-size: .75em;
  border-bottom: .5px solid;
  text-transform: uppercase;
  font-weight: bold;
}

.article__readmore a:hover, .article__container a:hover {
  color: #00c58e;
  border-bottom: .5px solid;
}

.tags, .clearTags {
  padding: 0 10px;
  text-align: center;
  /* border-radius: 10px; */
  border: none;
  text-transform: uppercase;
  background-color: #22eeb4; /* 6ae0bf */
  font-size: .7em;
  color: black;
  margin-right: .5em;
  opacity: .9;
}

.clearTags {
  background-color: #ff961e;
}

.tags:hover, .clearTags:hover {
  opacity: 1;
}

.selectedTags {
  margin-bottom: 10vh;
}

.tagTitle  {
  text-transform: uppercase;
  font-size: .75em;
  color: white;
}

.article__updatedAt {
  font-size: .85em;
}

.tagClose {
  margin-left: 5px;
}
.tagClose:hover {
  font-weight: bold;
}

</style>