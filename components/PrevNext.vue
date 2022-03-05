<template>
  <div class="prev_next">
    <NuxtLink
      v-if="prev"
      :to="{ name: 'work-slug', params: { slug: prev.slug } }"
      class="prev"
    >&lt; {{ prev.title }}</NuxtLink>
    <span v-else>&nbsp;</span>
    <NuxtLink
      v-if="next"
      :to="{ name: 'work-slug', params: { slug: next.slug } }"
      class="next"
    >{{ next.title }} &gt;</NuxtLink>
    <span v-else>&nbsp;</span>
  </div>
</template>

<script>
  export default {
    props: {
      prev: {
        type: Object,
        default: () => null
      },
      next: {
        type: Object,
        default: () => null
      }
    }
  }
</script>

<style>
.next, .prev {
  text-decoration: none;
  text-transform: uppercase;
  color: white;
  font-size: .85em;
}

.next:hover, .prev:hover {
  color: #00c58e;
  border-bottom: .5px solid;
}

.next {
  float: right;
}

</style>