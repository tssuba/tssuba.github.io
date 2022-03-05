<template>
  <div class="resume__language">
    <div class="resume__section_title resume__language_title">&sect; {{ title }} </div>
    <div class="resume__content resume__to_space"> 
      <div v-for="(i, idx) in type" :key="idx">
        <span>{{ i }} ({{ proficiency[idx] }})</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      title: 'Languages',
      type: ['English', 'Hindi'], 
      proficiency: ['native','native']
    }
  }
  
}
</script>
