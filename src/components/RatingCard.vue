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
.card {
    width: 320px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: var(--light-grey);
    padding: 20px;
    background-color: var(--dark-blue);
    border-radius: 15px;
}

.card h1 {
    color: var(--white)
}

form {
    display: grid;
    row-gap: 5px;
}
.rating-input {
    appearance: none;
    display: grid;
    grid-row: 1;
    place-items: center;

    --size: 40px;
    width: var(--size);
    height: var(--size);
    color: var(--light-grey);

    transition: .5s all;
}

.rating-input:checked {
    background-color: var(--medium-grey);
    color: var(--white);
}

.rating-input:hover {
    background-color: var(--orange);
    color: var(--white);
    cursor: pointer;
}

.rating-input::before {
    content: attr(value);
    font-family: 'Overpass', sans-serif;
}

.submit-btn {
    grid-column: 1/6;
    width: 100%;
    background-color: var(--orange);
    padding: 10px;
    margin-top: 10px;
    font-weight: 700;
    color: var(--white);
    text-transform: uppercase;
    
    border: 0px;
    border-radius: 30px;
    
    transition: .5s all;
}

.submit-btn:hover {
    background-color: var(--white);
    color: var(--orange);
    cursor: pointer;
}

.message-thank-you > * {
    text-align: center;
    margin: 0;
}

.message-rating img, .rating-input {
    background-color: var(--dark-grey);
    border-radius: 50%;
    padding: 10px;
}

.feedback {
    width: fit-content;
    margin: auto auto 30px auto;
}
.feedback p {
    padding: 5px 15px;
    color: var(--orange);
    background-color: var(--dark-grey);
    border-radius: 25px;
}

@media (width < 375px) {
    .card {
        width: 220px;
    }

    h1 {
        font-size: 1.4em;
    }

    p {
        font-size: .8em;
    }

    .rating-input {
        --size: 30px;
        padding: 3px;
    }
}

</style>