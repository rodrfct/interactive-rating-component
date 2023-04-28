<script setup>

defineProps({
    rating: {
        type: Number,
        required: true
    }
})

defineEmits(['user-rated'])

let userRating = 0


</script>

<template>
    <div class="card">
        <div v-if="!userRating" class="message-rating">
            <img src="../assets/img/icon-star.svg" alt="">

            <h1>How did we do?</h1>

            <p>
                Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!
            </p>

            <form @submit.prevent="$emit('user-rated', userRating)">
                <input type="radio" name="rating-input" value="1" v-model="userRating">
                <input type="radio" name="rating-input" value="2" v-model="userRating">
                <input type="radio" name="rating-input" value="3" v-model="userRating">
                <input type="radio" name="rating-input" value="4" v-model="userRating">
                <input type="radio" name="rating-input" value="5" v-model="userRating">

                <button type="submit" class="submit-btn">Submit</button>
            </form>
        </div>

        <div v-else class="message-thank-you">
            <div class="feedback">
                <img src="../assets/img/illustration-thank-you.svg" alt="">
                <p>You selected {{ userRating }} out of 5</p>
            </div>

            <h1>Thank You!</h1>

            <p>
                We appreciate you taking the time to give a rating. If you ever need more support, don’t hesitate to get in touch!
            </p>
        </div>
    </div>
</template>

<style scoped>
:root {
    --very-dark-blue: hsl(216, 12%, 8%)
}
.card {
    background-color: var(--very-dark-blue);
    border-radius: 30px;
}
</style>