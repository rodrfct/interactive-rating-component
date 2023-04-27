<script setup>

defineProps({
    rated: {
        type: Boolean,
        required: true
    },

    rating: {
        type: Number,
        required: true
    }
})
</script>

<template>
    <div class="card">
        <div v-if="!rated" class="message-rating">
            <img src="../assets/img/icon-star.svg" alt="">

            <h1>How did we do?</h1>

            <p>
                Please let us know how we did with your support request. All feedback is appreciated to help us improve our offering!
            </p>

            <ul>
                <li class="rate">1</li>
                <li class="rate">2</li>
                <li class="rate">3</li>
                <li class="rate">4</li>
                <li class="rate">5</li>
            </ul>

            <button class="submit-btn">Submit</button>
        </div>

        <div v-else class="message-thank-you">
            <div class="feedback">
                <img src="../assets/img/illustration-thank-you.svg" alt="">
                <p>You selected {{ rating }} out of 5</p>
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