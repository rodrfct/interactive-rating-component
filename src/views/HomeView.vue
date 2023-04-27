<script setup>
  import RatingCard from '../components/RatingCard.vue';

  let rated = false
</script>

<template>
  <main>

    <RatingCard :rated="rated" />
    
    <div class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
      Coded by <a href="#">Your Name Here</a>.
    </div>
  </main>
</template>
