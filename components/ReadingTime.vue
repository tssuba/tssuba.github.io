<template>
  <span class="readingTime">{{ readingTime}} MIN READ</span>
</template>

<script>
export default {
  props: ['content'],
  computed: {
    readingTime () {
      let mins = 0; 
      const contentString = JSON.stringify(this.content);
      const words = contentString.split(' ').length;
      const wordsPerMin = 200; 
      
      mins = Math.ceil(words / wordsPerMin);

      return mins; 
    }
  }
}
</script>

<style>
.readingTime {
  font-size: .85em;
}

</style>