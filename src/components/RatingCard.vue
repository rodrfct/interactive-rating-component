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
                <input type="radio" name="rating-input" class="rating-input" value="1" v-model="userRating">
                <input type="radio" name="rating-input" class="rating-input" value="2" v-model="userRating">
                <input type="radio" name="rating-input" class="rating-input" value="3" v-model="userRating">
                <input type="radio" name="rating-input" class="rating-input" value="4" v-model="userRating">
                <input type="radio" name="rating-input" class="rating-input" value="5" v-model="userRating">

                <button type="submit" class="submit-btn">SUBMIT</button>
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
.card {
    width: 330px;
    margin: auto;
    color: var(--light-grey);
    padding: 20px;
    background-color: var(--very-dark-blue);
    border-radius: 30px;
}

.card h1 {
    color: var(--white)
}

.rating-input {
    appearance: none;
    --size: 40px;
    width: var(--size);
    height: var(--size);
    margin: 13px;
    color: var(--light-grey);
}

.rating-input::before {
    content: attr(value);
    margin-left: 6px;
    font-family: 'Overpass', sans-serif;
}

.submit-btn {
    display: block;
    font-weight: 700;
    color: var(--white);
    width: 100%;
    padding: 10px;
    background-color: var(--orange);
    border: 0px;
    border-radius: 30px;
}

.message-thank-you > * {
    text-align: center;
}

.message-rating img, .rating-input {
    background-color: var(--dark-blue);
    border-radius: 50%;
    padding: 10px;
}

.feedback p {
    color: var(--orange);
    background-color: var(--medium-grey);
}

</style>