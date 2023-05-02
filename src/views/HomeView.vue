<script setup>
  import { ref } from 'vue';
  import RatingCard from '../components/RatingCard.vue';

  let rating = ref(0)
</script>

<template>
  <main>

    <RatingCard :rating="rating" @user-rated="rating = userRating" />
    
    <div class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
      Coded by <a href="https://github.com/rodrfct">rodrfct</a>.
    </div>
  </main>
</template>
